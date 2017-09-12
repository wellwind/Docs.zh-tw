---
title: "ASP.NET Core 中的 Razor 頁面簡介"
author: Rick-Anderson
description: "ASP.NET Core 中的 Razor 頁面概觀"
keywords: "ASP.NET Core, Razor 頁面"
ms.author: riande
manager: wpickett
ms.date: 08/15/2017
ms.topic: get-started-article
ms.technology: aspnet
ms.prod: asp.net-core
uid: mvc/razor-pages/index
ms.openlocfilehash: 543399d99af127f943f7e9119fb5d84c8c5bc499
ms.sourcegitcommit: 9cdbfd0d670d70b9c354216aabee260c52dad5ee
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2017
---
# <a name="introduction-to-razor-pages-in-aspnet-core"></a><span data-ttu-id="08e80-104">ASP.NET Core 中的 Razor 頁面簡介</span><span class="sxs-lookup"><span data-stu-id="08e80-104">Introduction to Razor Pages in ASP.NET Core</span></span>

<span data-ttu-id="08e80-105">作者：[Rick Anderson](https://twitter.com/RickAndMSFT) 與 [Ryan Nowak](https://github.com/rynowak)</span><span class="sxs-lookup"><span data-stu-id="08e80-105">By [Rick Anderson](https://twitter.com/RickAndMSFT) and [Ryan Nowak](https://github.com/rynowak)</span></span>

<span data-ttu-id="08e80-106">Razor 頁面是 ASP.NET Core MVC 的新功能，更容易編寫以頁面為焦點的案例程式碼，也更具生產力。</span><span class="sxs-lookup"><span data-stu-id="08e80-106">Razor Pages is a new feature of ASP.NET Core MVC that makes coding page-focused scenarios easier and more productive.</span></span>

<span data-ttu-id="08e80-107">如果您在尋找使用模型檢視控制器方法的教學課程，請參閱 [ASP.NET Core MVC 使用者入門](xref:tutorials/first-mvc-app/start-mvc)。</span><span class="sxs-lookup"><span data-stu-id="08e80-107">If you're looking for a tutorial that uses the Model-View-Controller approach, see [Getting started with ASP.NET Core MVC](xref:tutorials/first-mvc-app/start-mvc).</span></span>

<a name="prerequisites"></a>

## <a name="aspnet-core-20-prerequisites"></a><span data-ttu-id="08e80-108">ASP.NET Core 2.0 必要條件</span><span class="sxs-lookup"><span data-stu-id="08e80-108">ASP.NET Core 2.0 prerequisites</span></span>

<span data-ttu-id="08e80-109">安裝 [.NET Core](https://www.microsoft.com/net/core) 2.0.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="08e80-109">Install [.NET Core](https://www.microsoft.com/net/core) 2.0.0 or later.</span></span>

<span data-ttu-id="08e80-110">如果您使用的是 Visual Studio，請安裝 [Visual Studio](https://www.visualstudio.com/vs/) 15.3 或更新版本，加上下列工作負載：</span><span class="sxs-lookup"><span data-stu-id="08e80-110">If you're using Visual Studio, install [Visual Studio](https://www.visualstudio.com/vs/) 15.3 or later with the following workloads:</span></span>

* <span data-ttu-id="08e80-111">**ASP.NET 與網頁程式開發**</span><span class="sxs-lookup"><span data-stu-id="08e80-111">**ASP.NET and web development**</span></span>
* <span data-ttu-id="08e80-112">**.NET Core 跨平台開發**</span><span class="sxs-lookup"><span data-stu-id="08e80-112">**.NET Core cross-platform development**</span></span>

<a name="rpvs17"></a>

## <a name="creating-a-razor-pages-project"></a><span data-ttu-id="08e80-113">建立 Razor 頁面專案</span><span class="sxs-lookup"><span data-stu-id="08e80-113">Creating a Razor Pages project</span></span>

# <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="08e80-114">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="08e80-114">Visual Studio</span></span>](#tab/visual-studio) 

<span data-ttu-id="08e80-115">如需如何使用 Visual Studio 建立 Razor 頁面專案的詳細說明，請參閱[開始使用 Razor 頁面](xref:tutorials/razor-pages/razor-pages-start)。</span><span class="sxs-lookup"><span data-stu-id="08e80-115">See [Getting started with Razor Pages](xref:tutorials/razor-pages/razor-pages-start) for detailed instructions on how to create a Razor Pages project using Visual Studio.</span></span>

#   <a name="visual-studio-for-mactabvisual-studio-mac"></a>[<span data-ttu-id="08e80-116">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="08e80-116">Visual Studio for Mac</span></span>](#tab/visual-studio-mac)

<span data-ttu-id="08e80-117">從命令列執行 `dotnet new razor`。</span><span class="sxs-lookup"><span data-stu-id="08e80-117">Run `dotnet new razor` from the command line.</span></span>

<span data-ttu-id="08e80-118">從 Visual Studio for Mac 開啟已產生的 *.csproj* 檔案。</span><span class="sxs-lookup"><span data-stu-id="08e80-118">Open the generated *.csproj* file from Visual Studio for Mac.</span></span>

# <a name="visual-studio-codetabvisual-studio-code"></a>[<span data-ttu-id="08e80-119">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="08e80-119">Visual Studio Code</span></span>](#tab/visual-studio-code) 

<span data-ttu-id="08e80-120">從命令列執行 `dotnet new razor`。</span><span class="sxs-lookup"><span data-stu-id="08e80-120">Run `dotnet new razor` from the command line.</span></span>

#   <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="08e80-121">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="08e80-121">.NET Core CLI</span></span>](#tab/netcore-cli) 

<span data-ttu-id="08e80-122">從命令列執行 `dotnet new razor`。</span><span class="sxs-lookup"><span data-stu-id="08e80-122">Run `dotnet new razor` from the command line.</span></span>

---

## <a name="razor-pages"></a><span data-ttu-id="08e80-123">Razor 頁面</span><span class="sxs-lookup"><span data-stu-id="08e80-123">Razor Pages</span></span>

<span data-ttu-id="08e80-124">Razor 頁面是在 *Startup.cs* 中啟用：</span><span class="sxs-lookup"><span data-stu-id="08e80-124">Razor Pages is enabled in *Startup.cs*:</span></span>

<span data-ttu-id="08e80-125">[!code-cs[main](index/sample/RazorPagesIntro/Startup.cs?name=Startup)]</span><span class="sxs-lookup"><span data-stu-id="08e80-125">[!code-cs[main](index/sample/RazorPagesIntro/Startup.cs?name=Startup)]</span></span>

<span data-ttu-id="08e80-126">請考慮使用基本頁面：<a name="OnGet"></a></span><span class="sxs-lookup"><span data-stu-id="08e80-126">Consider a basic page: <a name="OnGet"></a></span></span>

<span data-ttu-id="08e80-127">[!code-cshtml[main](index/sample/RazorPagesIntro/Pages/Index.cshtml)]</span><span class="sxs-lookup"><span data-stu-id="08e80-127">[!code-cshtml[main](index/sample/RazorPagesIntro/Pages/Index.cshtml)]</span></span>

<span data-ttu-id="08e80-128">上述程式碼看起來很像 Razor 檢視檔案。</span><span class="sxs-lookup"><span data-stu-id="08e80-128">The preceding code looks a lot like a Razor view file.</span></span> <span data-ttu-id="08e80-129">讓它不同的是 `@page` 指示詞。</span><span class="sxs-lookup"><span data-stu-id="08e80-129">What makes it different is the `@page` directive.</span></span> <span data-ttu-id="08e80-130">`@page` 會將檔案轉換成 MVC 動作，這表示它會直接處理要求，不用透過控制器。</span><span class="sxs-lookup"><span data-stu-id="08e80-130">`@page` makes the file into an MVC action - which means that it handles requests directly, without going through a controller.</span></span> <span data-ttu-id="08e80-131">`@page` 必須是頁面上的第一個 Razor 指示詞。</span><span class="sxs-lookup"><span data-stu-id="08e80-131">`@page` must be the first Razor directive on a page.</span></span> <span data-ttu-id="08e80-132">`@page` 會影響其他的 Razor 建構行為。</span><span class="sxs-lookup"><span data-stu-id="08e80-132">`@page` affects the behavior of other Razor constructs.</span></span> <span data-ttu-id="08e80-133">[@functions](xref:mvc/views/razor#functions) 指示詞可啟用函式層級的內容。</span><span class="sxs-lookup"><span data-stu-id="08e80-133">The [@functions](xref:mvc/views/razor#functions) directive enables function-level content.</span></span>

<span data-ttu-id="08e80-134">下列兩個檔案會顯示類似的頁面，但 `PageModel` 在不同的檔案中。</span><span class="sxs-lookup"><span data-stu-id="08e80-134">A similar page, with the `PageModel` in a separate file, is shown in the following two files.</span></span> <span data-ttu-id="08e80-135">*Pages/Index2.cshtml* 檔案：</span><span class="sxs-lookup"><span data-stu-id="08e80-135">The *Pages/Index2.cshtml* file:</span></span>

<span data-ttu-id="08e80-136">[!code-cshtml[main](index/sample/RazorPagesIntro/Pages/Index2.cshtml)]</span><span class="sxs-lookup"><span data-stu-id="08e80-136">[!code-cshtml[main](index/sample/RazorPagesIntro/Pages/Index2.cshtml)]</span></span>

<span data-ttu-id="08e80-137">*Pages/Index2.cshtml.cs*「程式碼後置」檔案：</span><span class="sxs-lookup"><span data-stu-id="08e80-137">The *Pages/Index2.cshtml.cs* 'code-behind' file:</span></span>

<span data-ttu-id="08e80-138">[!code-cs[main](index/sample/RazorPagesIntro/Pages/Index2.cshtml.cs)]</span><span class="sxs-lookup"><span data-stu-id="08e80-138">[!code-cs[main](index/sample/RazorPagesIntro/Pages/Index2.cshtml.cs)]</span></span>

<span data-ttu-id="08e80-139">依照慣例，`PageModel` 類別檔和附加 *.cs* 檔名的 Razor 頁面檔案名稱相同。</span><span class="sxs-lookup"><span data-stu-id="08e80-139">By convention, the `PageModel` class file has the same name as the Razor Page file with *.cs* appended.</span></span> <span data-ttu-id="08e80-140">例如，前一個 Razor 頁面是 *Pages/Index2.cshtml*。</span><span class="sxs-lookup"><span data-stu-id="08e80-140">For example, the previous Razor Page is *Pages/Index2.cshtml*.</span></span> <span data-ttu-id="08e80-141">包含 `PageModel` 類別的檔案名為 *Pages/Index2.cshtml.cs*。</span><span class="sxs-lookup"><span data-stu-id="08e80-141">The file containing the `PageModel` class is named *Pages/Index2.cshtml.cs*.</span></span>

<span data-ttu-id="08e80-142">至於簡單的頁面，混合 `PageModel` 類別加上 Razor 標記是正常的。</span><span class="sxs-lookup"><span data-stu-id="08e80-142">For simple pages, mixing the `PageModel` class with the Razor markup is fine.</span></span> <span data-ttu-id="08e80-143">至於更複雜的程式碼，最佳做法是分開頁面模型程式碼。</span><span class="sxs-lookup"><span data-stu-id="08e80-143">For more complex code, it's a best practice to keep the page model code separate.</span></span>

<span data-ttu-id="08e80-144">頁面的 URL 路徑關聯是由頁面在檔案系統中的位置決定。</span><span class="sxs-lookup"><span data-stu-id="08e80-144">The associations of URL paths to pages are determined by the page's location in the file system.</span></span> <span data-ttu-id="08e80-145">下表顯示 Razor 頁面路徑和相符的 URL：</span><span class="sxs-lookup"><span data-stu-id="08e80-145">The following table shows a Razor Page path and the matching URL:</span></span>

| <span data-ttu-id="08e80-146">檔案名稱和路徑</span><span class="sxs-lookup"><span data-stu-id="08e80-146">File name and path</span></span>               | <span data-ttu-id="08e80-147">比對 URL</span><span class="sxs-lookup"><span data-stu-id="08e80-147">matching URL</span></span> |
| ----------------- | ------------ |
| <span data-ttu-id="08e80-148">*/Pages/Index.cshtml*</span><span class="sxs-lookup"><span data-stu-id="08e80-148">*/Pages/Index.cshtml*</span></span> | <span data-ttu-id="08e80-149">`/` 或 `/Index`</span><span class="sxs-lookup"><span data-stu-id="08e80-149">`/` or `/Index`</span></span> |
| <span data-ttu-id="08e80-150">*/Pages/Contact.cshtml*</span><span class="sxs-lookup"><span data-stu-id="08e80-150">*/Pages/Contact.cshtml*</span></span> | `/Contact` |
| <span data-ttu-id="08e80-151">*/Pages/Store/Contact.cshtml*</span><span class="sxs-lookup"><span data-stu-id="08e80-151">*/Pages/Store/Contact.cshtml*</span></span> | `/Store/Contact` |
| <span data-ttu-id="08e80-152">*/Pages/Store/Index.cshtml*</span><span class="sxs-lookup"><span data-stu-id="08e80-152">*/Pages/Store/Index.cshtml*</span></span> | <span data-ttu-id="08e80-153">`/Store` 或 `/Store/Index`</span><span class="sxs-lookup"><span data-stu-id="08e80-153">`/Store` or `/Store/Index`</span></span>  |

<span data-ttu-id="08e80-154">附註：</span><span class="sxs-lookup"><span data-stu-id="08e80-154">Notes:</span></span>

* <span data-ttu-id="08e80-155">執行階段預設會在 *Pages* 資料夾中尋找 Razor 頁面的檔案。</span><span class="sxs-lookup"><span data-stu-id="08e80-155">The runtime looks for Razor Pages files in the *Pages* folder by default.</span></span>
* <span data-ttu-id="08e80-156">`Index` 是 URL 未包含頁面時的預設頁面。</span><span class="sxs-lookup"><span data-stu-id="08e80-156">`Index` is the default page when a URL doesn't include a page.</span></span>

## <a name="writing-a-basic-form"></a><span data-ttu-id="08e80-157">撰寫基本表單</span><span class="sxs-lookup"><span data-stu-id="08e80-157">Writing a basic form</span></span>

<span data-ttu-id="08e80-158">Razor 頁面功能旨在讓常見模式容易搭配網頁瀏覽器使用。</span><span class="sxs-lookup"><span data-stu-id="08e80-158">Razor Pages features are designed to make common patterns used with web browsers easy.</span></span> <span data-ttu-id="08e80-159">[模型繫結](xref:mvc/models/model-binding)、[標記協助程式](xref:mvc/views/tag-helpers/intro)和 HTML 協助程式搭配 Razor 頁面類別中定義的屬性「就這麼簡單」。</span><span class="sxs-lookup"><span data-stu-id="08e80-159">[Model binding](xref:mvc/models/model-binding), [Tag Helpers](xref:mvc/views/tag-helpers/intro), and HTML helpers all *just work* with the properties defined in a Razor Page class.</span></span> <span data-ttu-id="08e80-160">`Contact` 模型請考慮實作基本的「與我們連絡」格式頁面：</span><span class="sxs-lookup"><span data-stu-id="08e80-160">Consider a page that implements a basic "contact us" form for the `Contact` model:</span></span>

<span data-ttu-id="08e80-161">本文件中的範例，會在 [Startup.cs](https://github.com/aspnet/Docs/blob/master/aspnetcore/mvc/razor-pages/index/sample/RazorPagesContacts/Startup.cs#L15-L16) 檔案中初始化 `DbContext`。</span><span class="sxs-lookup"><span data-stu-id="08e80-161">For the samples in this document, the `DbContext` is initialized in the [Startup.cs](https://github.com/aspnet/Docs/blob/master/aspnetcore/mvc/razor-pages/index/sample/RazorPagesContacts/Startup.cs#L15-L16) file.</span></span>

<span data-ttu-id="08e80-162">[!code-cs[main](index/sample/RazorPagesContacts/Startup.cs?highlight=15-16)]</span><span class="sxs-lookup"><span data-stu-id="08e80-162">[!code-cs[main](index/sample/RazorPagesContacts/Startup.cs?highlight=15-16)]</span></span>

<span data-ttu-id="08e80-163">資料模型：</span><span class="sxs-lookup"><span data-stu-id="08e80-163">The data model:</span></span>

<span data-ttu-id="08e80-164">[!code-cs[main](index/sample/RazorPagesContacts/Data/Customer.cs)]</span><span class="sxs-lookup"><span data-stu-id="08e80-164">[!code-cs[main](index/sample/RazorPagesContacts/Data/Customer.cs)]</span></span>

<span data-ttu-id="08e80-165">*Pages/Create.cshtml* 檢視檔案：</span><span class="sxs-lookup"><span data-stu-id="08e80-165">The *Pages/Create.cshtml* view file:</span></span>

<span data-ttu-id="08e80-166">[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Create.cshtml)]</span><span class="sxs-lookup"><span data-stu-id="08e80-166">[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Create.cshtml)]</span></span>

<span data-ttu-id="08e80-167">*Pages/Create.cshtml.cs* 程式碼後置檔案供檢視之用：</span><span class="sxs-lookup"><span data-stu-id="08e80-167">The *Pages/Create.cshtml.cs* code-behind file for the view:</span></span>

<span data-ttu-id="08e80-168">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=ALL)]</span><span class="sxs-lookup"><span data-stu-id="08e80-168">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=ALL)]</span></span>

<span data-ttu-id="08e80-169">依照慣例，`PageModel` 類別稱之為 `<PageName>Model`，與頁面位於相同的命名空間。</span><span class="sxs-lookup"><span data-stu-id="08e80-169">By convention, the `PageModel` class is called `<PageName>Model` and is in the same namespace as the page.</span></span> <span data-ttu-id="08e80-170">從使用 `@functions` 定義處理常式的頁面和使用 `PageModel` 類別的頁面轉換，不需要太多變更。</span><span class="sxs-lookup"><span data-stu-id="08e80-170">Not much change is needed to convert from a page using `@functions` to define handlers and a page using a `PageModel` class.</span></span>

<span data-ttu-id="08e80-171">使用 `PageModel` 程式碼後置檔案可支援單元測試，但需要撰寫明確的建構函式和類別。</span><span class="sxs-lookup"><span data-stu-id="08e80-171">Using a `PageModel` code-behind file supports unit testing, but requires you to write an explicit constructor and class.</span></span> <span data-ttu-id="08e80-172">沒有 `PageModel` 程式碼後置檔案的頁面支援執行階段編譯，這會是開發中的優勢。</span><span class="sxs-lookup"><span data-stu-id="08e80-172">Pages without `PageModel` code-behind files support runtime compilation, which can be an advantage in development.</span></span>  <!-- review: advantage because you can make changes and refresh the browser without explicitly compiling the app -->

<span data-ttu-id="08e80-173">在 `POST` 要求上執行的頁面具有 `OnPostAsync`「處理常式方法」 (當使用者張貼表單時)。</span><span class="sxs-lookup"><span data-stu-id="08e80-173">The page has an `OnPostAsync` *handler method*, which runs on `POST` requests (when a user posts the form).</span></span> <span data-ttu-id="08e80-174">您可以新增任何 HTTP 指令動詞的處理常式方法。</span><span class="sxs-lookup"><span data-stu-id="08e80-174">You can add handler methods for any HTTP verb.</span></span> <span data-ttu-id="08e80-175">最常見的處理常式包括：</span><span class="sxs-lookup"><span data-stu-id="08e80-175">The most common handlers are:</span></span>

* <span data-ttu-id="08e80-176">`OnGet`，初始化頁所需要的狀態。</span><span class="sxs-lookup"><span data-stu-id="08e80-176">`OnGet` to initialize state needed for the page.</span></span> <span data-ttu-id="08e80-177">[OnGet](#OnGet) 範例。</span><span class="sxs-lookup"><span data-stu-id="08e80-177">[OnGet](#OnGet) sample.</span></span>
* <span data-ttu-id="08e80-178">`OnPost`，處理表單提交作業。</span><span class="sxs-lookup"><span data-stu-id="08e80-178">`OnPost` to handle form submissions.</span></span>

<span data-ttu-id="08e80-179">`Async` 命名尾碼是選擇性的，但依照慣例通常用於非同步函式。</span><span class="sxs-lookup"><span data-stu-id="08e80-179">The `Async` naming suffix is optional but is often used by convention for asynchronous functions.</span></span> <span data-ttu-id="08e80-180">上例中的 `OnPostAsync` 程式碼看起來類似您一般在控制器中撰寫的內容。</span><span class="sxs-lookup"><span data-stu-id="08e80-180">The `OnPostAsync` code in the preceding example looks similar to what you would normally write in a controller.</span></span> <span data-ttu-id="08e80-181">上述程式碼一般用於 Razor 頁面。</span><span class="sxs-lookup"><span data-stu-id="08e80-181">The preceding code is typical for Razor Pages.</span></span> <span data-ttu-id="08e80-182">大部分的基本 MVC，像是[模型繫結](xref:mvc/models/model-binding)、[驗證](xref:mvc/models/validation)和動作結果都是共用的。</span><span class="sxs-lookup"><span data-stu-id="08e80-182">Most of the MVC primitives like [model binding](xref:mvc/models/model-binding), [validation](xref:mvc/models/validation), and action results are shared.</span></span>  <!-- Review: Ryan, can we get a list of what is shared and what isn't? -->

<span data-ttu-id="08e80-183">前一個 `OnPostAsync` 方法：</span><span class="sxs-lookup"><span data-stu-id="08e80-183">The previous `OnPostAsync` method:</span></span>

<span data-ttu-id="08e80-184">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=OnPostAsync)]</span><span class="sxs-lookup"><span data-stu-id="08e80-184">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=OnPostAsync)]</span></span>

<span data-ttu-id="08e80-185">`OnPostAsync` 的基本流程：</span><span class="sxs-lookup"><span data-stu-id="08e80-185">The basic flow of `OnPostAsync`:</span></span>

<span data-ttu-id="08e80-186">檢查驗證錯誤。</span><span class="sxs-lookup"><span data-stu-id="08e80-186">Check for validation errors.</span></span>

*  <span data-ttu-id="08e80-187">如果沒有任何錯誤，會儲存資料並重新導向。</span><span class="sxs-lookup"><span data-stu-id="08e80-187">If there are no errors, save the data and redirect.</span></span>
*  <span data-ttu-id="08e80-188">如果有錯誤，會再次顯示有驗證訊息的頁面。</span><span class="sxs-lookup"><span data-stu-id="08e80-188">If there are errors, show the page again with validation messages.</span></span> <span data-ttu-id="08e80-189">用戶端驗證和傳統的 ASP.NET Core MVC 應用程式完全相同。</span><span class="sxs-lookup"><span data-stu-id="08e80-189">Client-side validation is identical to traditional ASP.NET Core MVC applications.</span></span> <span data-ttu-id="08e80-190">在許多情況下，用戶端會偵測到驗證錯誤，但從不提交給伺服器。</span><span class="sxs-lookup"><span data-stu-id="08e80-190">In many cases, validation errors would be detected on the client, and never submitted to the server.</span></span>

<span data-ttu-id="08e80-191">成功輸入資料後，`OnPostAsync` 處理常式方法會呼叫 `RedirectToPage` 協助程式方法，傳回 `RedirectToPageResult` 的執行個體。</span><span class="sxs-lookup"><span data-stu-id="08e80-191">When the data is entered successfully, the `OnPostAsync` handler method calls the `RedirectToPage` helper method to return an instance of `RedirectToPageResult`.</span></span> <span data-ttu-id="08e80-192">`RedirectToPage` 是新的動作結果，類似於 `RedirectToAction` 或 `RedirectToRoute`，但會針對頁面自訂。</span><span class="sxs-lookup"><span data-stu-id="08e80-192">`RedirectToPage` is a new action result, similar to `RedirectToAction` or `RedirectToRoute`, but customized for pages.</span></span> <span data-ttu-id="08e80-193">在上述範例中，它會重新導向至根索引頁面 (`/Index`)。</span><span class="sxs-lookup"><span data-stu-id="08e80-193">In the preceding sample, it redirects to the root Index page (`/Index`).</span></span> <span data-ttu-id="08e80-194">[產生頁面 URL](#url_gen)一節會詳細說明 `RedirectToPage`。</span><span class="sxs-lookup"><span data-stu-id="08e80-194">`RedirectToPage` is detailed in the [URL generation for Pages](#url_gen) section.</span></span>

<span data-ttu-id="08e80-195">當提交的表單有驗證錯誤時 (傳遞至伺服器)，`OnPostAsync` 處理常式方法會呼叫 `Page` 協助程式方法。</span><span class="sxs-lookup"><span data-stu-id="08e80-195">When the submitted form has validation errors (that are passed to the server), the`OnPostAsync` handler method calls the `Page` helper method.</span></span> <span data-ttu-id="08e80-196">`Page` 傳回 `PageResult` 的執行個體。</span><span class="sxs-lookup"><span data-stu-id="08e80-196">`Page` returns an instance of `PageResult`.</span></span> <span data-ttu-id="08e80-197">傳回 `Page` 類似於控制站中的動作傳回 `View`。</span><span class="sxs-lookup"><span data-stu-id="08e80-197">Returning `Page` is similar to how actions in controllers return `View`.</span></span> <span data-ttu-id="08e80-198">`PageResult` 是處理常式方法的預設 <!-- Review  --> 傳回型別。</span><span class="sxs-lookup"><span data-stu-id="08e80-198">`PageResult` is the default <!-- Review  --> return type for a handler method.</span></span> <span data-ttu-id="08e80-199">傳回 `void` 的處理常式方法會呈現頁面。</span><span class="sxs-lookup"><span data-stu-id="08e80-199">A handler method that returns `void` renders the page.</span></span>

<span data-ttu-id="08e80-200">`Customer` 屬性 (property) 使用 `[BindProperty]` 屬性 (attribute) 加入模型繫結。</span><span class="sxs-lookup"><span data-stu-id="08e80-200">The `Customer` property uses `[BindProperty]` attribute to opt in to model binding.</span></span>

<span data-ttu-id="08e80-201">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=PageModel&highlight=10-11)]</span><span class="sxs-lookup"><span data-stu-id="08e80-201">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=PageModel&highlight=10-11)]</span></span>

<span data-ttu-id="08e80-202">Razor 頁面預設只繫結屬性和非 GET 指令動詞。</span><span class="sxs-lookup"><span data-stu-id="08e80-202">Razor Pages, by default, bind properties only with non-GET verbs.</span></span> <span data-ttu-id="08e80-203">繫結至屬性可以減少您必須撰寫的程式碼數量。</span><span class="sxs-lookup"><span data-stu-id="08e80-203">Binding to properties can reduce the amount of code you have to write.</span></span> <span data-ttu-id="08e80-204">透過使用相同的屬性呈現表單欄位 (`<input asp-for="Customer.Name" />`) 並接受輸入，繫結可以減少程式碼。</span><span class="sxs-lookup"><span data-stu-id="08e80-204">Binding reduces code by using the same property to render form fields (`<input asp-for="Customer.Name" />`) and accept the input.</span></span>

<span data-ttu-id="08e80-205">下列程式碼顯示建立頁面的合併版本：</span><span class="sxs-lookup"><span data-stu-id="08e80-205">The following code shows the combined version of the create page:</span></span>

<span data-ttu-id="08e80-206">[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/CreateCombined.cshtml)]</span><span class="sxs-lookup"><span data-stu-id="08e80-206">[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/CreateCombined.cshtml)]</span></span>

<span data-ttu-id="08e80-207">我們要利用頁面的新功能，而不是使用 `@model`。</span><span class="sxs-lookup"><span data-stu-id="08e80-207">Rather than using `@model`, we're taking advantage of a new feature for Pages.</span></span> <span data-ttu-id="08e80-208">根據預設，產生的 `Page` 衍生類別「是」模型。</span><span class="sxs-lookup"><span data-stu-id="08e80-208">By default, the generated `Page`-derived class *is* the model.</span></span> <span data-ttu-id="08e80-209">使用「檢視模型」搭配 Razor 檢視是最佳做法。</span><span class="sxs-lookup"><span data-stu-id="08e80-209">Using a *view model* with Razor views is a best practice.</span></span> <span data-ttu-id="08e80-210">透過頁面，您可以「自動」取得檢視模型。</span><span class="sxs-lookup"><span data-stu-id="08e80-210">With Pages, you get a view model *automatically*.</span></span>

<span data-ttu-id="08e80-211">主要的變更是以插入的 (`@inject`) 屬性取代建構函式插入。</span><span class="sxs-lookup"><span data-stu-id="08e80-211">The main change is replacing constructor injection with injected (`@inject`) properties.</span></span> <span data-ttu-id="08e80-212">此頁面會使用 [@inject ](xref:mvc/views/razor#inject) 處理[建構函式相依性插入](xref:mvc/controllers/dependency-injection#constructor-injection)。</span><span class="sxs-lookup"><span data-stu-id="08e80-212">This page uses [@inject](xref:mvc/views/razor#inject) for [constructor dependency injection](xref:mvc/controllers/dependency-injection#constructor-injection).</span></span> <span data-ttu-id="08e80-213">`@inject` 陳述式會產生並初始化用於 `OnPostAsync` 中的 `Db` 屬性。</span><span class="sxs-lookup"><span data-stu-id="08e80-213">The `@inject` statement generates and initializes the `Db` property that is used in `OnPostAsync`.</span></span> <span data-ttu-id="08e80-214">插入的 (`@inject`) 屬性會在處理常式方法執行之前設定。</span><span class="sxs-lookup"><span data-stu-id="08e80-214">Injected (`@inject`) properties are set before handler methods run.</span></span>


<span data-ttu-id="08e80-215">首頁 (*Index.cshtml*)：</span><span class="sxs-lookup"><span data-stu-id="08e80-215">The home page (*Index.cshtml*):</span></span>

<span data-ttu-id="08e80-216">[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Index.cshtml)]</span><span class="sxs-lookup"><span data-stu-id="08e80-216">[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Index.cshtml)]</span></span>

<span data-ttu-id="08e80-217">程式碼後置 *Index.cshtml.cs* 檔案：</span><span class="sxs-lookup"><span data-stu-id="08e80-217">The code behind *Index.cshtml.cs* file:</span></span>

<span data-ttu-id="08e80-218">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Index.cshtml.cs)]</span><span class="sxs-lookup"><span data-stu-id="08e80-218">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Index.cshtml.cs)]</span></span>

<span data-ttu-id="08e80-219">*Index.cshtml* 檔案包含下列標記可為每個連絡人建立編輯連結：</span><span class="sxs-lookup"><span data-stu-id="08e80-219">The *Index.cshtml* file contains the following markup to create an edit link for each contact:</span></span>

```html
<a asp-page="./Edit" asp-route-id="@contact.Id">edit</a>
```

<span data-ttu-id="08e80-220">[錨定標記協助程式](xref:mvc/views/tag-helpers/builtin-th/AnchorTagHelper)過去使用 [asp-route-{value}](xref:mvc/views/tag-helpers/builtin-th/AnchorTagHelper#route) 屬性產生 [編輯] 頁面的連結。</span><span class="sxs-lookup"><span data-stu-id="08e80-220">The [Anchor Tag Helper](xref:mvc/views/tag-helpers/builtin-th/AnchorTagHelper) used the [asp-route-{value}](xref:mvc/views/tag-helpers/builtin-th/AnchorTagHelper#route) attribute to generate a link to the Edit page.</span></span> <span data-ttu-id="08e80-221">該連結包含路由資料和連絡人識別碼。</span><span class="sxs-lookup"><span data-stu-id="08e80-221">The link contains route data with the contact ID.</span></span> <span data-ttu-id="08e80-222">例如，`http://localhost:5000/Edit/1`。</span><span class="sxs-lookup"><span data-stu-id="08e80-222">For example, `http://localhost:5000/Edit/1`.</span></span>

<span data-ttu-id="08e80-223">*Pages/Edit.cshtml* 檔案：</span><span class="sxs-lookup"><span data-stu-id="08e80-223">The *Pages/Edit.cshtml* file:</span></span>

<span data-ttu-id="08e80-224">[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Edit.cshtml?highlight=1)]</span><span class="sxs-lookup"><span data-stu-id="08e80-224">[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Edit.cshtml?highlight=1)]</span></span>

<span data-ttu-id="08e80-225">第一行包含 `@page "{id:int}"` 指示詞。</span><span class="sxs-lookup"><span data-stu-id="08e80-225">The first line contains the `@page "{id:int}"` directive.</span></span> <span data-ttu-id="08e80-226">路由條件約束 `"{id:int}"` 通知頁面接受包含 `int` 路由資料的頁面要求。</span><span class="sxs-lookup"><span data-stu-id="08e80-226">The routing constraint`"{id:int}"` tells the page to accept requests to the page that contain `int` route data.</span></span> <span data-ttu-id="08e80-227">如果頁面要求不包含可以轉換成 `int` 的路由資料，執行階段會傳回 HTTP 404 (找不到) 錯誤。</span><span class="sxs-lookup"><span data-stu-id="08e80-227">If a request to the page doesn't contain route data that can be converted to an `int`, the runtime returns an HTTP 404 (not found) error.</span></span>

<span data-ttu-id="08e80-228">*Pages/Edit.cshtml.cs* 檔案：</span><span class="sxs-lookup"><span data-stu-id="08e80-228">The *Pages/Edit.cshtml.cs* file:</span></span>

<span data-ttu-id="08e80-229">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Edit.cshtml.cs)]</span><span class="sxs-lookup"><span data-stu-id="08e80-229">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Edit.cshtml.cs)]</span></span>

<a name="xsrf"></a>

## <a name="xsrfcsrf-and-razor-pages"></a><span data-ttu-id="08e80-230">XSRF/CSRF 和 Razor 頁面</span><span class="sxs-lookup"><span data-stu-id="08e80-230">XSRF/CSRF and Razor Pages</span></span>

<span data-ttu-id="08e80-231">您不必撰寫任何[防偽驗證](xref:security/anti-request-forgery)程式碼。</span><span class="sxs-lookup"><span data-stu-id="08e80-231">You don't have to write any code for [antiforgery validation](xref:security/anti-request-forgery).</span></span> <span data-ttu-id="08e80-232">防偽權杖的產生和驗證會自動包含在 Razor 頁面中。</span><span class="sxs-lookup"><span data-stu-id="08e80-232">Antiforgery token generation and validation are automatically included in Razor Pages.</span></span>

<a name="layout"></a>
## <a name="using-layouts-partials-templates-and-tag-helpers-with-razor-pages"></a><span data-ttu-id="08e80-233">搭配 Razor 頁面使用版面配置、部分、範本和標記協助程式。</span><span class="sxs-lookup"><span data-stu-id="08e80-233">Using Layouts, partials, templates, and Tag Helpers with Razor Pages</span></span>

<span data-ttu-id="08e80-234">頁面使用 Razor 檢視引擎的所有功能。</span><span class="sxs-lookup"><span data-stu-id="08e80-234">Pages work with all the features of the Razor view engine.</span></span> <span data-ttu-id="08e80-235">版面配置、部分、範本、標記協助程式、*_ViewStart.cshtml*、*_ViewImports.cshtml* 運作方式一如它們在傳統 Razor 檢視中的方式。</span><span class="sxs-lookup"><span data-stu-id="08e80-235">Layouts, partials, templates, Tag Helpers, *_ViewStart.cshtml*, *_ViewImports.cshtml* work in the same way they do for conventional Razor views.</span></span>

<span data-ttu-id="08e80-236">利用這些功能的一部分來清理此頁面。</span><span class="sxs-lookup"><span data-stu-id="08e80-236">Let's declutter this page by taking advantage of some of those features.</span></span>

<span data-ttu-id="08e80-237">將[版面配置頁面](xref:mvc/views/layout)新增至 *Pages/_Layout.cshtml*：</span><span class="sxs-lookup"><span data-stu-id="08e80-237">Add a [layout page](xref:mvc/views/layout) to *Pages/_Layout.cshtml*:</span></span>

<span data-ttu-id="08e80-238">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_LayoutSimple.cshtml)]</span><span class="sxs-lookup"><span data-stu-id="08e80-238">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_LayoutSimple.cshtml)]</span></span>

<span data-ttu-id="08e80-239">[配置](xref:mvc/views/layout)：</span><span class="sxs-lookup"><span data-stu-id="08e80-239">The [Layout](xref:mvc/views/layout):</span></span>

* <span data-ttu-id="08e80-240">控制每個頁面的版面配置 (除非頁面退出版面配置)。</span><span class="sxs-lookup"><span data-stu-id="08e80-240">Controls the layout of each page (unless the page opts out of layout).</span></span>
* <span data-ttu-id="08e80-241">匯入 HTML 結構，例如 JavaScript 和樣式表。</span><span class="sxs-lookup"><span data-stu-id="08e80-241">Imports HTML structures such as JavaScript and stylesheets.</span></span>

<span data-ttu-id="08e80-242">如需詳細資訊，請參閱[版面配置頁面](xref:mvc/views/layout)。</span><span class="sxs-lookup"><span data-stu-id="08e80-242">See [layout page](xref:mvc/views/layout) for more information.</span></span>

<span data-ttu-id="08e80-243">[版面配置](xref:mvc/views/layout#specifying-a-layout)屬性是在 *Pages/_ViewStart.cshtml* 中設定：</span><span class="sxs-lookup"><span data-stu-id="08e80-243">The [Layout](xref:mvc/views/layout#specifying-a-layout) property is set in *Pages/_ViewStart.cshtml*:</span></span>

<span data-ttu-id="08e80-244">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_ViewStart.cshtml)]</span><span class="sxs-lookup"><span data-stu-id="08e80-244">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_ViewStart.cshtml)]</span></span>

<span data-ttu-id="08e80-245">注意：版面配置是在 *Pages* 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="08e80-245">Note: The layout is in the *Pages* folder.</span></span> <span data-ttu-id="08e80-246">頁面會以階層方式尋找其他檢視 (版面配置、範本、部分)，從目前頁面的相同資料夾開始。</span><span class="sxs-lookup"><span data-stu-id="08e80-246">Pages look for other views (layouts, templates, partials) hierarchically, starting in the same folder as the current page.</span></span> <span data-ttu-id="08e80-247">您可以從任何 Razor 頁面下的 *Pages* 資料夾中，使用 *Pages* 資料夾中的版面配置。</span><span class="sxs-lookup"><span data-stu-id="08e80-247">A layout in the *Pages* folder can be used from any Razor page under the *Pages* folder.</span></span>

<span data-ttu-id="08e80-248">我們**不**建議您將配置檔案放入 *Views/Shared* 資料夾。</span><span class="sxs-lookup"><span data-stu-id="08e80-248">We recommend you **not** put the layout file in the *Views/Shared* folder.</span></span> <span data-ttu-id="08e80-249">*Views/Shared* 是 MVC 檢視模式。</span><span class="sxs-lookup"><span data-stu-id="08e80-249">*Views/Shared* is an MVC views pattern.</span></span> <span data-ttu-id="08e80-250">Razor 頁面應該要依賴資料夾階層，不是路徑慣例。</span><span class="sxs-lookup"><span data-stu-id="08e80-250">Razor Pages are meant to rely on folder hierarchy, not path conventions.</span></span>

<span data-ttu-id="08e80-251">Razor 頁面的檢視搜尋包括 *Pages* 資料夾。</span><span class="sxs-lookup"><span data-stu-id="08e80-251">View search from a Razor Page includes the *Pages* folder.</span></span> <span data-ttu-id="08e80-252">搭配 MVC 控制器使用的版面配置、範本和部分以及傳統的 Razor 檢視「就這麼簡單」。</span><span class="sxs-lookup"><span data-stu-id="08e80-252">The layouts, templates, and partials you're using with MVC controllers and conventional Razor views *just work*.</span></span>

<span data-ttu-id="08e80-253">新增 *Pages/_ViewImports.cshtml* 檔案：</span><span class="sxs-lookup"><span data-stu-id="08e80-253">Add a *Pages/_ViewImports.cshtml* file:</span></span>

<span data-ttu-id="08e80-254">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_ViewImports.cshtml)]</span><span class="sxs-lookup"><span data-stu-id="08e80-254">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_ViewImports.cshtml)]</span></span>

<span data-ttu-id="08e80-255">本教學課程稍後會說明 `@namespace`。</span><span class="sxs-lookup"><span data-stu-id="08e80-255">`@namespace` is explained later in the tutorial.</span></span> <span data-ttu-id="08e80-256">`@addTagHelper` 指示詞會將[內建標記協助程式](xref:mvc/views/tag-helpers/builtin-th/Index)帶入 *Pages* 資料夾中的所有頁面。</span><span class="sxs-lookup"><span data-stu-id="08e80-256">The `@addTagHelper` directive brings in the [built-in Tag Helpers](xref:mvc/views/tag-helpers/builtin-th/Index) to all the pages in the *Pages* folder.</span></span>

<a name="namespace"></a>

<span data-ttu-id="08e80-257">在頁面上明確使用 `@namespace` 指示詞時：</span><span class="sxs-lookup"><span data-stu-id="08e80-257">When the `@namespace` directive is used explicitly on a page:</span></span>

<span data-ttu-id="08e80-258">[!code-cshtml[main](index/sample/RazorPagesIntro/Pages/Customers/Namespace2.cshtml?highlight=2)]</span><span class="sxs-lookup"><span data-stu-id="08e80-258">[!code-cshtml[main](index/sample/RazorPagesIntro/Pages/Customers/Namespace2.cshtml?highlight=2)]</span></span>

<span data-ttu-id="08e80-259">指示詞會設定頁面的命名空間。</span><span class="sxs-lookup"><span data-stu-id="08e80-259">The directive sets the namespace for the page.</span></span> <span data-ttu-id="08e80-260">`@model` 指示詞不需要包含命名空間。</span><span class="sxs-lookup"><span data-stu-id="08e80-260">The `@model` directive doesn't need to include the namespace.</span></span>

<span data-ttu-id="08e80-261">當 `@namespace` 指示詞包含在 *_ViewImports.cshtml* 中時，指定的命名空間會在匯入 `@namespace` 指示詞的頁面中提供所產生之命名空間的前置詞。</span><span class="sxs-lookup"><span data-stu-id="08e80-261">When the `@namespace` directive is contained in *_ViewImports.cshtml*, the specified namespace supplies the prefix for the generated namespace in the Page that imports the `@namespace` directive.</span></span> <span data-ttu-id="08e80-262">所產生命名空間的其餘部分 (後置字元部分) 是包含 *_ViewImports.cshtml* 的資料夾和包含頁面的資料夾之間，以句點分隔的相對路徑。</span><span class="sxs-lookup"><span data-stu-id="08e80-262">The rest of the generated namespace (the suffix portion) is the dot-separated relative path between the folder containing *_ViewImports.cshtml* and the folder containing the page.</span></span>

<span data-ttu-id="08e80-263">例如，程式碼後置檔案*Pages/Customers/Edit.cshtml.cs* 會以明確方式設定命名空間：</span><span class="sxs-lookup"><span data-stu-id="08e80-263">For example, the code behind file *Pages/Customers/Edit.cshtml.cs* explicitly sets the namespace:</span></span>

<span data-ttu-id="08e80-264">[!code-cs[main](index/sample/RazorPagesContacts2/Pages/Customers/Edit.cshtml.cs?name=namespace)]</span><span class="sxs-lookup"><span data-stu-id="08e80-264">[!code-cs[main](index/sample/RazorPagesContacts2/Pages/Customers/Edit.cshtml.cs?name=namespace)]</span></span>

<span data-ttu-id="08e80-265">*Pages/_ViewImports.cshtml* 檔案會設定下列命名空間：</span><span class="sxs-lookup"><span data-stu-id="08e80-265">The *Pages/_ViewImports.cshtml* file sets the following namespace:</span></span>

<span data-ttu-id="08e80-266">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_ViewImports.cshtml?highlight=1)]</span><span class="sxs-lookup"><span data-stu-id="08e80-266">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_ViewImports.cshtml?highlight=1)]</span></span>

<span data-ttu-id="08e80-267">針對 *Pages/Customers/Edit.cshtml* Razor 頁面產生的命名空間和程式碼後置檔案相同。</span><span class="sxs-lookup"><span data-stu-id="08e80-267">The generated namespace for the *Pages/Customers/Edit.cshtml* Razor Page is the same as the code behind file.</span></span> <span data-ttu-id="08e80-268">`@namespace` 指示詞的設計是為了將 C# 類別新增至專案，頁面產生的程式碼「就這麼簡單」，不必為程式碼後置檔案新增 `@using` 指示詞。</span><span class="sxs-lookup"><span data-stu-id="08e80-268">The `@namespace` directive was designed so the C# classes added to a project and pages-generated code *just work* without having to add an `@using` directive for the code behind file.</span></span>

<span data-ttu-id="08e80-269">注意：`@namespace` 也適用於傳統的 Razor 檢視。</span><span class="sxs-lookup"><span data-stu-id="08e80-269">Note: `@namespace` also works with conventional Razor views.</span></span>

<span data-ttu-id="08e80-270">原始的 *Pages/Create.cshtml* 檢視檔案：</span><span class="sxs-lookup"><span data-stu-id="08e80-270">The original *Pages/Create.cshtml* view file:</span></span>

<span data-ttu-id="08e80-271">[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Create.cshtml?highlight=2)]</span><span class="sxs-lookup"><span data-stu-id="08e80-271">[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Create.cshtml?highlight=2)]</span></span>

<span data-ttu-id="08e80-272">更新的頁面：</span><span class="sxs-lookup"><span data-stu-id="08e80-272">The updated page:</span></span>

<span data-ttu-id="08e80-273">*Pages/Create.cshtml* 檢視檔案：</span><span class="sxs-lookup"><span data-stu-id="08e80-273">The *Pages/Create.cshtml* view file:</span></span>

<span data-ttu-id="08e80-274">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/Create.cshtml?highlight=2)]</span><span class="sxs-lookup"><span data-stu-id="08e80-274">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/Create.cshtml?highlight=2)]</span></span>

<span data-ttu-id="08e80-275">[Razor 頁面入門專案](#rpvs17)包含 *Pages/_ValidationScriptsPartial.cshtml*，連結用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="08e80-275">The [Razor Pages starter project](#rpvs17) contains the *Pages/_ValidationScriptsPartial.cshtml*, which hooks up client-side validation.</span></span>

<a name="url_gen"></a>

## <a name="url-generation-for-pages"></a><span data-ttu-id="08e80-276">產生頁面 URL</span><span class="sxs-lookup"><span data-stu-id="08e80-276">URL generation for Pages</span></span>

<span data-ttu-id="08e80-277">前面出現過的 `Create` 頁面使用 `RedirectToPage`：</span><span class="sxs-lookup"><span data-stu-id="08e80-277">The `Create` page, shown previously, uses `RedirectToPage`:</span></span>

<span data-ttu-id="08e80-278">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=OnPostAsync&highlight=10)]</span><span class="sxs-lookup"><span data-stu-id="08e80-278">[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=OnPostAsync&highlight=10)]</span></span>

<span data-ttu-id="08e80-279">應用程式有下列檔案/資料夾結構</span><span class="sxs-lookup"><span data-stu-id="08e80-279">The app has the following file/folder structure</span></span>

* <span data-ttu-id="08e80-280">*/Pages*</span><span class="sxs-lookup"><span data-stu-id="08e80-280">*/Pages*</span></span>

  * <span data-ttu-id="08e80-281">*Index.cshtml*</span><span class="sxs-lookup"><span data-stu-id="08e80-281">*Index.cshtml*</span></span>
  * <span data-ttu-id="08e80-282">*/Customer*</span><span class="sxs-lookup"><span data-stu-id="08e80-282">*/Customer*</span></span>

    * <span data-ttu-id="08e80-283">*Create.cshtml*</span><span class="sxs-lookup"><span data-stu-id="08e80-283">*Create.cshtml*</span></span>
    * <span data-ttu-id="08e80-284">*Edit.cshtml*</span><span class="sxs-lookup"><span data-stu-id="08e80-284">*Edit.cshtml*</span></span>
    * <span data-ttu-id="08e80-285">*Index.cshtml*</span><span class="sxs-lookup"><span data-stu-id="08e80-285">*Index.cshtml*</span></span>

<span data-ttu-id="08e80-286">*Pages/Customers/Create.cshtml* 和 *Pages/Customers/Edit.cshtml* 頁面在成功後會重新導向至 *Pages/Index.cshtml*。</span><span class="sxs-lookup"><span data-stu-id="08e80-286">The *Pages/Customers/Create.cshtml* and *Pages/Customers/Edit.cshtml* pages redirect to *Pages/Index.cshtml* after success.</span></span> <span data-ttu-id="08e80-287">字串 `/Index` 為 URI 的一部分，可存取前一個頁面。</span><span class="sxs-lookup"><span data-stu-id="08e80-287">The string `/Index` is part of the URI to access the preceding page.</span></span> <span data-ttu-id="08e80-288">字串 `/Index` 可以用來產生 *Pages/Index.cshtml* 頁面的 URI。</span><span class="sxs-lookup"><span data-stu-id="08e80-288">The string `/Index` can be used to generate URIs to the *Pages/Index.cshtml* page.</span></span> <span data-ttu-id="08e80-289">例如: </span><span class="sxs-lookup"><span data-stu-id="08e80-289">For example:</span></span>

* `Url.Page("/Index", ...)`
* `<a asp-page="/Index">My Index Page</a>`
* `RedirectToPage("/Index")`

<span data-ttu-id="08e80-290">頁面名稱是來自根 */Pages* 資料夾的頁面路徑 (包括前置的 `/`，例如 `/Index`)。</span><span class="sxs-lookup"><span data-stu-id="08e80-290">The page name is the path to the page from the root */Pages* folder (including a leading `/`, for example `/Index`).</span></span> <span data-ttu-id="08e80-291">上述的 URL 產生範例比僅有硬式編碼的 URL 更有特色。</span><span class="sxs-lookup"><span data-stu-id="08e80-291">The preceding URL generation samples are much more feature rich than just hardcoding a URL.</span></span> <span data-ttu-id="08e80-292">URL 產生使用[路由](xref:mvc/controllers/routing)，可以根據路由在目的地路徑中定義的方式，產生並且編碼參數。</span><span class="sxs-lookup"><span data-stu-id="08e80-292">URL generation uses [routing](xref:mvc/controllers/routing) and can generate and encode parameters according to how the route is defined in the destination path.</span></span>

<span data-ttu-id="08e80-293">產生頁面 URL 支援相關的名稱。</span><span class="sxs-lookup"><span data-stu-id="08e80-293">URL generation for pages supports relative names.</span></span> <span data-ttu-id="08e80-294">下表顯示從 *Pages/Customers/Create.cshtml* 以不同的 `RedirectToPage` 參數選取的索引頁：</span><span class="sxs-lookup"><span data-stu-id="08e80-294">The following table shows which Index page is selected with different `RedirectToPage` parameters from *Pages/Customers/Create.cshtml*:</span></span>

| <span data-ttu-id="08e80-295">RedirectToPage(x)</span><span class="sxs-lookup"><span data-stu-id="08e80-295">RedirectToPage(x)</span></span>| <span data-ttu-id="08e80-296">頁面</span><span class="sxs-lookup"><span data-stu-id="08e80-296">Page</span></span> |
| ----------------- | ------------ |
| <span data-ttu-id="08e80-297">RedirectToPage("/Index")</span><span class="sxs-lookup"><span data-stu-id="08e80-297">RedirectToPage("/Index")</span></span> | <span data-ttu-id="08e80-298">*Pages/Index*</span><span class="sxs-lookup"><span data-stu-id="08e80-298">*Pages/Index*</span></span> |
| <span data-ttu-id="08e80-299">RedirectToPage("./Index");</span><span class="sxs-lookup"><span data-stu-id="08e80-299">RedirectToPage("./Index");</span></span> | <span data-ttu-id="08e80-300">*Pages/Customers/Index*</span><span class="sxs-lookup"><span data-stu-id="08e80-300">*Pages/Customers/Index*</span></span> |
| <span data-ttu-id="08e80-301">RedirectToPage("../Index")</span><span class="sxs-lookup"><span data-stu-id="08e80-301">RedirectToPage("../Index")</span></span> | <span data-ttu-id="08e80-302">*Pages/Index*</span><span class="sxs-lookup"><span data-stu-id="08e80-302">*Pages/Index*</span></span> |
| <span data-ttu-id="08e80-303">RedirectToPage("Index")</span><span class="sxs-lookup"><span data-stu-id="08e80-303">RedirectToPage("Index")</span></span>  | <span data-ttu-id="08e80-304">*Pages/Customers/Index*</span><span class="sxs-lookup"><span data-stu-id="08e80-304">*Pages/Customers/Index*</span></span> |

<span data-ttu-id="08e80-305">`RedirectToPage("Index")`、`RedirectToPage("./Index")` 和 `RedirectToPage("../Index")` 是「相對名稱」。</span><span class="sxs-lookup"><span data-stu-id="08e80-305">`RedirectToPage("Index")`, `RedirectToPage("./Index")`, and `RedirectToPage("../Index")`  are *relative names*.</span></span> <span data-ttu-id="08e80-306">`RedirectToPage` 參數「結合」了目前頁面的路徑，以計算目的地頁面的名稱。</span><span class="sxs-lookup"><span data-stu-id="08e80-306">The `RedirectToPage` parameter is *combined* with the path of the current page to compute the name of the destination page.</span></span>  <!-- Review: Original had The provided string is combined with the page name of the current page to compute the name of the destination page. -- page name, not page path -->

<span data-ttu-id="08e80-307">相對名稱連結在以複雜結構建置網站時很有用。</span><span class="sxs-lookup"><span data-stu-id="08e80-307">Relative name linking is useful when building sites with a complex structure.</span></span> <span data-ttu-id="08e80-308">如果您使用相對名稱連結資料夾中的頁面，您可以重新命名該資料夾。</span><span class="sxs-lookup"><span data-stu-id="08e80-308">If you use relative names to link between pages in a folder, you can rename that folder.</span></span> <span data-ttu-id="08e80-309">所有連結仍可運作 (因為它們不包含資料夾名稱)。</span><span class="sxs-lookup"><span data-stu-id="08e80-309">All the links still work (because they didn't include the folder name).</span></span>

## <a name="tempdata"></a><span data-ttu-id="08e80-310">TempData</span><span class="sxs-lookup"><span data-stu-id="08e80-310">TempData</span></span>

<span data-ttu-id="08e80-311">ASP.NET Core 公開[控制器](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.controller)上的 [TempData](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.controller#Microsoft_AspNetCore_Mvc_Controller_TempData) 屬性。</span><span class="sxs-lookup"><span data-stu-id="08e80-311">ASP.NET Core exposes the [TempData](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.controller#Microsoft_AspNetCore_Mvc_Controller_TempData) property on a [controller](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.controller).</span></span> <span data-ttu-id="08e80-312">這個屬性會儲存資料，直到讀取為止。</span><span class="sxs-lookup"><span data-stu-id="08e80-312">This property stores data until it is read.</span></span> <span data-ttu-id="08e80-313">`Keep` 和 `Peek` 方法可以用來檢查資料，不用刪除。</span><span class="sxs-lookup"><span data-stu-id="08e80-313">The `Keep` and `Peek` methods can be used to examine the data without deletion.</span></span> <span data-ttu-id="08e80-314">當有多個要求需要資料時，`TempData` 對重新導向很有幫助。</span><span class="sxs-lookup"><span data-stu-id="08e80-314">`TempData` is  useful for redirection, when data is needed for more than a single request.</span></span>

<span data-ttu-id="08e80-315">`[TempData]` 是 ASP.NET Core 2.0 的新屬性，在控制站和頁面都受支援。</span><span class="sxs-lookup"><span data-stu-id="08e80-315">The `[TempData]` attribute is new in ASP.NET Core 2.0 and is supported on controllers and pages.</span></span>

<span data-ttu-id="08e80-316">下列程式碼會設定使用 `TempData` 的 `Message` 值。</span><span class="sxs-lookup"><span data-stu-id="08e80-316">The following code sets the value of `Message` using `TempData`.</span></span>
<span data-ttu-id="08e80-317">[!code-cs[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateDot.cshtml.cs?highlight=10-11,27-28&name=snippetTemp)]</span><span class="sxs-lookup"><span data-stu-id="08e80-317">[!code-cs[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateDot.cshtml.cs?highlight=10-11,27-28&name=snippetTemp)]</span></span>

<span data-ttu-id="08e80-318">*Pages/Customers/Index.cshtml* 檔案中的下列標記會顯示使用 `TempData` 的 `Message` 值。</span><span class="sxs-lookup"><span data-stu-id="08e80-318">The following markup in the *Pages/Customers/Index.cshtml* file displays the value of `Message` using `TempData`.</span></span>

```cshtml
<h3>Msg: @Model.Message</h3>
```

<span data-ttu-id="08e80-319">*Pages/Customers/Index.cshtml.cs* 程式碼後置檔案會將 `[TempData]` 屬性 (attribute) 套用到 `Message` 屬性 (property)。</span><span class="sxs-lookup"><span data-stu-id="08e80-319">The *Pages/Customers/Index.cshtml.cs* code-behind file applies the `[TempData]` attribute to the `Message` property.</span></span>

```cs
[TempData]
public string Message { get; set; }
```

<span data-ttu-id="08e80-320">如需詳細資訊，請參閱 [TempData](xref:fundamentals/app-state#temp)。</span><span class="sxs-lookup"><span data-stu-id="08e80-320">See [TempData](xref:fundamentals/app-state#temp) for more information.</span></span>

<a name="mhpp"></a>
## <a name="multiple-handlers-per-page"></a><span data-ttu-id="08e80-321">每頁面有多個處理常式</span><span class="sxs-lookup"><span data-stu-id="08e80-321">Multiple handlers per page</span></span>

<span data-ttu-id="08e80-322">下列頁面會使用 `asp-page-handler` 標記協助程式為兩個頁面處理常式產生標記：</span><span class="sxs-lookup"><span data-stu-id="08e80-322">The following page generates markup for two page handlers using the `asp-page-handler` Tag Helper:</span></span>

<span data-ttu-id="08e80-323">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateFATH.cshtml?highlight=12-13)]</span><span class="sxs-lookup"><span data-stu-id="08e80-323">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateFATH.cshtml?highlight=12-13)]</span></span>

<!-- Review: the FormActionTagHelper applies to all <form /> elements on a Razor page, even when there is no `asp-` attribute   -->

<span data-ttu-id="08e80-324">上例中的表單有兩個提交按鈕，每一個都使用 `FormActionTagHelper` 提交至不同的 URL。</span><span class="sxs-lookup"><span data-stu-id="08e80-324">The form in the preceding example has two submit buttons, each using the `FormActionTagHelper` to submit to a different URL.</span></span> <span data-ttu-id="08e80-325">`asp-page-handler` 屬性附隨於 `asp-page`。</span><span class="sxs-lookup"><span data-stu-id="08e80-325">The `asp-page-handler` attribute is a companion to `asp-page`.</span></span> <span data-ttu-id="08e80-326">`asp-page-handler` 產生的 URL 會提交至頁面所定義的每一個處理常式方法。</span><span class="sxs-lookup"><span data-stu-id="08e80-326">`asp-page-handler` generates URLs that submit to each of the handler methods defined by a page.</span></span> <span data-ttu-id="08e80-327">因為範例連結至目前的頁面，所以未指定 `asp-page`。</span><span class="sxs-lookup"><span data-stu-id="08e80-327">`asp-page` is not specified because the sample is linking to the current page.</span></span>

<span data-ttu-id="08e80-328">程式碼後置檔案：</span><span class="sxs-lookup"><span data-stu-id="08e80-328">The code-behind file:</span></span>

<span data-ttu-id="08e80-329">[!code-cs[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateFATH.cshtml.cs?highlight=20,32)]</span><span class="sxs-lookup"><span data-stu-id="08e80-329">[!code-cs[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateFATH.cshtml.cs?highlight=20,32)]</span></span>

<span data-ttu-id="08e80-330">上述程式碼使用「具名的處理常式方法」。</span><span class="sxs-lookup"><span data-stu-id="08e80-330">The preceding code uses *named handler methods*.</span></span> <span data-ttu-id="08e80-331">具名的處理常式方法的建立方式是採用名稱中在 `On<HTTP Verb>` 後面、`Async` 之前 (如有) 的文字。</span><span class="sxs-lookup"><span data-stu-id="08e80-331">Named handler methods are created by taking the text in the name after `On<HTTP Verb>` and before `Async` (if present).</span></span> <span data-ttu-id="08e80-332">在上例中，頁面方法是 OnPost**JoinList**Async 和 OnPost**JoinListUC**Async。</span><span class="sxs-lookup"><span data-stu-id="08e80-332">In the preceding example, the page methods are OnPost**JoinList**Async and OnPost**JoinListUC**Async.</span></span> <span data-ttu-id="08e80-333">移除 *OnPost* 和 *Async*，處理常式名稱就是 `JoinList` 和 `JoinListUC`。</span><span class="sxs-lookup"><span data-stu-id="08e80-333">With *OnPost* and *Async* removed, the handler names are `JoinList` and `JoinListUC`.</span></span>

<span data-ttu-id="08e80-334">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateFATH.cshtml?highlight=12-13)]</span><span class="sxs-lookup"><span data-stu-id="08e80-334">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateFATH.cshtml?highlight=12-13)]</span></span>

<span data-ttu-id="08e80-335">使用上述程式碼，提交至 `OnPostJoinListAsync` 的 URL 路徑是 `http://localhost:5000/Customers/CreateFATH?handler=JoinList`。</span><span class="sxs-lookup"><span data-stu-id="08e80-335">Using the preceding code, the URL path that submits to `OnPostJoinListAsync` is `http://localhost:5000/Customers/CreateFATH?handler=JoinList`.</span></span> <span data-ttu-id="08e80-336">提交至 `OnPostJoinListUCAsync` 的 URL 路徑是 `http://localhost:5000/Customers/CreateFATH?handler=JoinListUC`。</span><span class="sxs-lookup"><span data-stu-id="08e80-336">The URL path that submits to `OnPostJoinListUCAsync` is `http://localhost:5000/Customers/CreateFATH?handler=JoinListUC`.</span></span>

## <a name="customizing-routing"></a><span data-ttu-id="08e80-337">自訂路由</span><span class="sxs-lookup"><span data-stu-id="08e80-337">Customizing Routing</span></span>

<span data-ttu-id="08e80-338">如果您不喜歡 URL 有查詢字串 `?handler=JoinList`，您可以變更路由，將處理常式名稱置於 URL 的路徑部分。</span><span class="sxs-lookup"><span data-stu-id="08e80-338">If you don't like the query string `?handler=JoinList` in the URL, you can change the route to put the handler name in the path portion of the URL.</span></span> <span data-ttu-id="08e80-339">您可以新增路由範本，在 `@page` 指示詞後面用雙引號括住，以自訂路由。</span><span class="sxs-lookup"><span data-stu-id="08e80-339">You can customize the route by adding a route template enclosed in double quotes after the `@page` directive.</span></span>

<span data-ttu-id="08e80-340">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateRoute.cshtml?highlight=1)]</span><span class="sxs-lookup"><span data-stu-id="08e80-340">[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateRoute.cshtml?highlight=1)]</span></span>


<span data-ttu-id="08e80-341">上述的路由會將處理常式名稱放入 URL 路徑，而不是放入查詢字串。</span><span class="sxs-lookup"><span data-stu-id="08e80-341">The preceding route puts the handler name in the URL path instead of the query string.</span></span> <span data-ttu-id="08e80-342">跟在 `handler` 後面的 `?` 表示路由參數為選擇性。</span><span class="sxs-lookup"><span data-stu-id="08e80-342">The `?` following `handler` means the route parameter is optional.</span></span>

<span data-ttu-id="08e80-343">您可以使用 `@page` 將額外的區段和參數新增至頁面的路由。</span><span class="sxs-lookup"><span data-stu-id="08e80-343">You can use `@page` to add additional segments and parameters to a page's route.</span></span> <span data-ttu-id="08e80-344">無論什麼都**附加**至頁面的預設路由。</span><span class="sxs-lookup"><span data-stu-id="08e80-344">Whatever's there is **appended** to the default route of the page.</span></span> <span data-ttu-id="08e80-345">不支援使用絕對或虛擬路徑變更頁面的路由 (例如 `"~/Some/Other/Path"`)。</span><span class="sxs-lookup"><span data-stu-id="08e80-345">Using an absolute or virtual path to change the page's route (like `"~/Some/Other/Path"`) is not supported.</span></span>

## <a name="configuration-and-settings"></a><span data-ttu-id="08e80-346">組態與設定</span><span class="sxs-lookup"><span data-stu-id="08e80-346">Configuration and settings</span></span>

<span data-ttu-id="08e80-347">若要設定進階選項，請在 MVC 產生器上使用擴充方法 `AddRazorPagesOptions`：</span><span class="sxs-lookup"><span data-stu-id="08e80-347">To configure advanced options, use the extension method `AddRazorPagesOptions` on the MVC builder:</span></span>

<span data-ttu-id="08e80-348">[!code-cs[main](index/sample/RazorPagesContacts/StartupAdvanced.cs?name=snippet1)]</span><span class="sxs-lookup"><span data-stu-id="08e80-348">[!code-cs[main](index/sample/RazorPagesContacts/StartupAdvanced.cs?name=snippet1)]</span></span>

<span data-ttu-id="08e80-349">目前可以使用 `RazorPagesOptions` 設定頁面的根目錄，或新增頁面的應用程式模型慣例。</span><span class="sxs-lookup"><span data-stu-id="08e80-349">Currently you can use the `RazorPagesOptions` to set the root directory for pages, or add application model conventions for pages.</span></span> <span data-ttu-id="08e80-350">我們希望未來能以這種方式獲得更多的擴充性。</span><span class="sxs-lookup"><span data-stu-id="08e80-350">We hope to enable more extensibility this way in the future.</span></span>

<span data-ttu-id="08e80-351">若要先行編譯檢視，請參閱 [Razor 檢視編譯](xref:mvc/views/view-compilation)。</span><span class="sxs-lookup"><span data-stu-id="08e80-351">To precompile views, see [Razor view compilation](xref:mvc/views/view-compilation) .</span></span>

<span data-ttu-id="08e80-352">[下載或檢視範例程式碼](https://github.com/aspnet/Docs/tree/master/aspnetcore/mvc/razor-pages/index/sample)。</span><span class="sxs-lookup"><span data-stu-id="08e80-352">[Download or view sample code](https://github.com/aspnet/Docs/tree/master/aspnetcore/mvc/razor-pages/index/sample).</span></span>

<span data-ttu-id="08e80-353">請參閱根據本簡介建置的[開始使用 ASP.NET Core 中的 Razor 頁面](xref:tutorials/razor-pages/razor-pages-start)。</span><span class="sxs-lookup"><span data-stu-id="08e80-353">See [Getting started with Razor Pages in ASP.NET Core](xref:tutorials/razor-pages/razor-pages-start), which builds on this introduction.</span></span>