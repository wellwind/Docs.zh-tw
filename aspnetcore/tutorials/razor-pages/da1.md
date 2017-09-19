---
title: "更新產生的頁面"
author: rick-anderson
description: "以更好的顯示方式更新產生的網頁。"
keywords: "ASP.NET Core, Razor 頁面"
ms.author: riande
manager: wpickett
ms.date: 08/07/2017
ms.topic: get-started-article
ms.technology: aspnet
ms.prod: asp.net-core
uid: tutorials/razor-pages/da1
ms.openlocfilehash: 39b65f8af8304fabc6cf8d9a27992043f1e381a0
ms.sourcegitcommit: 9cdbfd0d670d70b9c354216aabee260c52dad5ee
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2017
---
# <a name="updating-the-generated-pages"></a>更新產生的頁面

作者：[Rick Anderson](https://twitter.com/RickAndMSFT)

我們開始使用電影應用程式的情況很不錯，但簡報卻不理想。 我們不想看到時間 (下圖的 12:00:00 AM)，而且 **ReleaseDate** 應該是 **Release Date** (兩個分開的字)。

![在 Chrome 中開啟的電影應用程式顯示電影資料](sql/_static/m55.png)

## <a name="update-the-generated-code"></a>更新產生的程式碼

開啟 *Models/Movie.cs* 檔案，然後新增下列程式碼中顯示的醒目提示行：

[!code-csharp[Main](razor-pages-start/sample/RazorPagesMovie/Models/MovieDate.cs?name=snippet_1&highlight=10-11)]

以滑鼠右鍵按一下紅色曲線 > **[快速動作與重構]**。

  ![操作功能表隨即顯示 **> [Quick Actions and Refactorings] (快速控制項目及重構)**。](da1/qa.png)


選取 `using System.ComponentModel.DataAnnotations;`。

  ![使用清單頂端的 System.ComponentModel.DataAnnotations](da1/da.png)

  Visual Studio 即會新增 `using System.ComponentModel.DataAnnotations;`。

接下來的教學課程中將涵蓋 [DataAnnotations](https://docs.microsoft.com/aspnet/mvc/overview/older-versions/mvc-music-store/mvc-music-store-part-6)。 [Display](https://docs.microsoft.com//aspnet/core/api/microsoft.aspnetcore.mvc.modelbinding.metadata.displaymetadata) 屬性指定要顯示的欄位名稱 (在本例中為 "Release Date"，而不是 "ReleaseDate")。 [DataType](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.dataannotations.internal.datatypeattributeadapter) 屬性指定資料的型別 (Date)，因此不會顯示儲存在欄位中的時間資訊。

瀏覽至 Pages/Movies，然後將滑鼠停留在 **Edit** 連結，以查看目標 URL。

![滑鼠停留在 Edit 連結並顯示 http://localhost:1234/Movies/Edit/5 的 Url 的瀏覽器視窗](da1/edit7.png)

在 *Pages/Movies/Index.cshtml* 檔案中，**Edit**、**Details ** 和 **Delete** 連結是由[錨點標記協助程式](xref:mvc/views/tag-helpers/builtin-th/AnchorTagHelper)所產生。

[!code-cshtml[Main](razor-pages-start\snapshot_sample\RazorPagesMovie\Pages\Movie\Index.cshtml?highlight=16-18&range=32-)]

[標記協助程式](xref:mvc/views/tag-helpers/intro)可啟用伺服器端程式碼，以參與建立和轉譯 Razor 檔案中的 HTML 元素。 在上述程式碼中，`AnchorTagHelper` 會從 Razor 頁面 (路由是相對路由)、`asp-page` 和路由識別碼 (`asp-route-id`) 動態產生 HTML `href` 屬性值。 如需詳細資訊，請參閱[頁面的 URL 產生](xref:mvc/razor-pages/index#url-generation-for-pages)。

從您最愛的瀏覽器中使用 [檢視原始檔] 來檢查產生的標記。 產生的 HTML 部分如下所示：

```html
<td>
  <a href="/Movies/Edit?id=1">Edit</a> |
  <a href="/Movies/Details?id=1">Details</a> |
  <a href="/Movies/Delete?id=1">Delete</a>
</td>

```

動態產生的連結會傳遞含有查詢字串的電影識別碼 (例如，`http://localhost:5000/Movies/Details?id=2`)。 

更新 Edit、Details 和 Delete Razor 頁面，以使用 "{id:int}" 路由範本。 將這些頁面每一頁的頁面指示詞變更為 `@page "{id:int}"`。 執行應用程式，然後檢視原始檔。 產生的 HTML 將識別碼新增至 URL 的路徑部分：

```html
<td>
  <a href="/Movies/Edit/1">Edit</a> |
  <a href="/Movies/Details/1">Details</a> |
  <a href="/Movies/Delete/1">Delete</a>
</td>
```

對使用 "{id:int}" 路由範本的頁面提出的要求若**未**包含整數，將傳回 HTTP 404 (找不到) 錯誤。 例如，`http://localhost:5000/Movies/Details` 會傳回 404 錯誤。 若要使識別碼成為選擇性，請將 `?` 附加至路由條件約束：

 ```cshtml
@page "{id:int?}"
```

### <a name="update-concurrency-exception-handling"></a>更新並行例外狀況處理

在 *Pages/Movies/Edit.cshtml.cs* 檔案中更新 `OnPostAsync` 方法。 下列醒目提示的程式碼示範這些變更：

[!code-csharp[Main](razor-pages-start/snapshot_sample/RazorPagesMovie/Pages/Movie/Edit.cshtml.cs?name=snippet1&highlight=17-24)]

當第一個並行用戶端刪除電影，而第二個並行用戶端發佈對電影的變更時，先前的程式碼只會偵測並行存取例外狀況。

若要測試 `catch` 區段：

* 在 `catch (DbUpdateConcurrencyException)` 上設定中斷點
* 編輯電影。
* 在另一個瀏覽器視窗中，選取相同電影的 **Delete** 連結，然後刪除電影。
* 在先前的瀏覽器視窗中，發佈對電影的變更。

生產環境程式碼通常會在兩個或多個用戶端同時更新一筆記錄時，偵測並行存取衝突。 如需詳細資訊，請參閱[處理並行存取衝突](xref:data/ef-mvc/concurrency)。

### <a name="posting-and-binding-review"></a>發佈和繫結檢閱內容

檢查 *Pages/Movies/Edit.cshtml.cs* 檔案：[!code-csharp[Main](razor-pages-start/snapshot_sample/RazorPagesMovie/Pages/Movie/Edit.cshtml.cs?name=snippet2)]

對 Movies/Edit 頁面提出 HTTP GET 要求時 (例如，`http://localhost:5000/Movies/Edit/2`)：

* `OnGetAsync` 方法會從資料庫擷取電影，並傳回 `Page` 方法。 
* `Page` 方法會轉譯 *Pages/Movies/Edit.cshtml* Razor 頁面。 *Pages/Movies/Edit.cshtml* 檔案包含模型指示詞 (`@model RazorPagesMovie.Pages.Movies.EditModel`)，這會讓電影模型可以在頁面上使用。
* Edit 表單會顯示來自電影的值。

發佈 Movies/Edit 頁面時：

* 頁面上的表單值會繫結至 `Movie` 屬性。 `[BindProperty]` 屬性可讓[模型繫結](xref:mvc/models/model-binding)。

```csharp
[BindProperty]
public Movie Movie { get; set; }
```

* 如果模型狀態中有錯誤 (例如，`ReleaseDate`無法轉換為 date)，則會以提交的值再次發佈表單。
* 如果沒有任何模型錯誤，則會儲存電影。

Index、Create 和 Delete Razor 頁面中的 HTTP GET 方法都會依循類似的模式。 Create Razor 頁面中的 HTTP POST `OnPostAsync` 方法，會依循與 Edit Razor 頁面中的 `OnPostAsync` 方法類似的模式。

搜尋會在接下來的教學課程中新增。

>[!div class="step-by-step"]
[上一步：使用 SQL Server LocalDB](xref:tutorials/razor-pages/sql)
[新增搜尋](xref:tutorials/razor-pages/search)