---
title: "使用 AngularJS 單一網頁應用程式 (SPAs)"
author: rick-anderson
description: "了解如何建置使用 AngularJS SPA 樣式 ASP.NET 應用程式"
keywords: "ASP.NET Core，AngularJS SPA"
ms.author: riande
manager: wpickett
ms.date: 10/14/2016
ms.topic: article
ms.assetid: 4b30576b-2718-4c39-9253-a59966747893
ms.technology: aspnet
ms.prod: asp.net-core
uid: client-side/angular
ms.custom: H1Hack27Feb2017
ms.openlocfilehash: 2c7929976f0c9f8284ab397b1a87d576bcdd15b0
ms.sourcegitcommit: 9cdbfd0d670d70b9c354216aabee260c52dad5ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2017
---
# <a name="using-angularjs-for-single-page-applications-spas-with-aspnet-core"></a><span data-ttu-id="22c74-104">使用 AngularJS 與 ASP.NET Core 單一網頁應用程式 (SPAs)</span><span class="sxs-lookup"><span data-stu-id="22c74-104">Using AngularJS for Single Page Applications (SPAs) with ASP.NET Core</span></span>


<span data-ttu-id="22c74-105">由[Venkata Koppaka](https://blog.falafel.com/falafel-software-recognized-sitefinity-website-year/)和[Scott Addie](https://scottaddie.com)</span><span class="sxs-lookup"><span data-stu-id="22c74-105">By [Venkata Koppaka](https://blog.falafel.com/falafel-software-recognized-sitefinity-website-year/) and [Scott Addie](https://scottaddie.com)</span></span>

<span data-ttu-id="22c74-106">在本文中，您將學習如何建置使用 AngularJS SPA 樣式 ASP.NET 應用程式。</span><span class="sxs-lookup"><span data-stu-id="22c74-106">In this article, you will learn how to build a SPA-style ASP.NET application using AngularJS.</span></span>

[<span data-ttu-id="22c74-107">檢視或下載範例程式碼</span><span class="sxs-lookup"><span data-stu-id="22c74-107">View or download sample code</span></span>](https://github.com/aspnet/Docs/tree/master/aspnetcore/client-side/angular/sample)

## <a name="what-is-angularjs"></a><span data-ttu-id="22c74-108">AngularJS 是什麼？</span><span class="sxs-lookup"><span data-stu-id="22c74-108">What is AngularJS?</span></span>

<span data-ttu-id="22c74-109">[AngularJS](https://angularjs.org/)是現代化的 JavaScript 架構，將來自 Google 通常用於使用單一頁面應用程式 (SPAs)。</span><span class="sxs-lookup"><span data-stu-id="22c74-109">[AngularJS](https://angularjs.org/) is a modern JavaScript framework from Google commonly used to work with Single Page Applications (SPAs).</span></span> <span data-ttu-id="22c74-110">AngularJS 開啟來源 MIT 授權，並可以在之後的 AngularJS 開發進度[其 GitHub 儲存機制](https://github.com/angular/angular.js)。</span><span class="sxs-lookup"><span data-stu-id="22c74-110">AngularJS is open sourced under MIT license, and the development progress of AngularJS can be followed on [its GitHub repository](https://github.com/angular/angular.js).</span></span> <span data-ttu-id="22c74-111">稱為 Angular 文件庫，因為 HTML 使用角度形狀的方括號。</span><span class="sxs-lookup"><span data-stu-id="22c74-111">The library is called Angular because HTML uses angular-shaped brackets.</span></span>

<span data-ttu-id="22c74-112">AngularJS 不是 DOM 操作程式庫，例如 jQuery，但是它會使用稱為 jQLite jQuery 的子集。</span><span class="sxs-lookup"><span data-stu-id="22c74-112">AngularJS is not a DOM manipulation library like jQuery, but it uses a subset of jQuery called jQLite.</span></span> <span data-ttu-id="22c74-113">AngularJS 主要根據您可以將它加入至 HTML 標記的宣告式 HTML 屬性。</span><span class="sxs-lookup"><span data-stu-id="22c74-113">AngularJS is primarily based on declarative HTML attributes that you can add to your HTML tags.</span></span> <span data-ttu-id="22c74-114">您可以在瀏覽器中使用嘗試 AngularJS[程式碼學校網站](https://www.codeschool.com/courses/shaping-up-with-angularjs)或[W3Schools 網站](https://www.w3schools.com/angular/)。</span><span class="sxs-lookup"><span data-stu-id="22c74-114">You can try AngularJS in your browser using the [Code School website](https://www.codeschool.com/courses/shaping-up-with-angularjs) or  [W3Schools website](https://www.w3schools.com/angular/).</span></span>

<span data-ttu-id="22c74-115">本文將重點放在 AngularJS Angular 標題的其中一些注意事項。</span><span class="sxs-lookup"><span data-stu-id="22c74-115">This article focuses on AngularJS with some notes on where Angular is heading.</span></span>

## <a name="getting-started"></a><span data-ttu-id="22c74-116">使用者入門</span><span class="sxs-lookup"><span data-stu-id="22c74-116">Getting started</span></span>

<span data-ttu-id="22c74-117">若要開始使用 AngularJS ASP.NET 應用程式中，您必須將它安裝為您專案的一部分，或者從內容傳遞網路 (CDN) 中參考它。</span><span class="sxs-lookup"><span data-stu-id="22c74-117">To start using AngularJS in your ASP.NET application, you must either install it as part of your project, or reference it from a content delivery network (CDN).</span></span>

### <a name="installation"></a><span data-ttu-id="22c74-118">安裝</span><span class="sxs-lookup"><span data-stu-id="22c74-118">Installation</span></span>

<span data-ttu-id="22c74-119">有幾種方式將 AngularJS 加入您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="22c74-119">There are several ways to add AngularJS to your application.</span></span> <span data-ttu-id="22c74-120">如果您在 Visual Studio 中開始新的 ASP.NET Core web 應用程式，您可以加入 AngularJS 使用內建[Bower](bower.md)支援。</span><span class="sxs-lookup"><span data-stu-id="22c74-120">If you’re starting a new ASP.NET Core web application in Visual Studio, you can add AngularJS using the built-in [Bower](bower.md) support.</span></span> <span data-ttu-id="22c74-121">開啟*bower.json*，並加入項目以`dependencies`屬性：</span><span class="sxs-lookup"><span data-stu-id="22c74-121">Open *bower.json*, and add an entry to the `dependencies` property:</span></span>

<a name=angular-bower-json></a>

<span data-ttu-id="22c74-122">[!code-json[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/bower.json?highlight=9)]</span><span class="sxs-lookup"><span data-stu-id="22c74-122">[!code-json[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/bower.json?highlight=9)]</span></span>

<span data-ttu-id="22c74-123">在儲存時*bower.json* Angular 的檔案將會安裝在您的專案*wwwroot/lib*資料夾。</span><span class="sxs-lookup"><span data-stu-id="22c74-123">Upon saving the *bower.json* file, Angular will be installed in your project's *wwwroot/lib* folder.</span></span> <span data-ttu-id="22c74-124">此外，它會列於`Dependencies/Bower`資料夾。</span><span class="sxs-lookup"><span data-stu-id="22c74-124">Additionally, it will be listed within the `Dependencies/Bower` folder.</span></span> <span data-ttu-id="22c74-125">請參閱下面的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="22c74-125">See the screenshot below.</span></span>

![使用 AngularJS 專案的方案總管](angular/_static/angular-solution-explorer.png)

<span data-ttu-id="22c74-127">接下來，加入`<script>`參考底部`<body>`HTML 頁面的區段或*_Layout.cshtml*檔案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22c74-127">Next, add a `<script>` reference to the bottom of the `<body>` section of your HTML page or *_Layout.cshtml* file, as shown here:</span></span>

<span data-ttu-id="22c74-128">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Shared/_Layout.cshtml?highlight=4&range=48-52)]</span><span class="sxs-lookup"><span data-stu-id="22c74-128">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Shared/_Layout.cshtml?highlight=4&range=48-52)]</span></span>

<span data-ttu-id="22c74-129">我們建議實際執行應用程式，利用像 AngularJS 的通用程式庫的 Cdn。</span><span class="sxs-lookup"><span data-stu-id="22c74-129">It's recommended that production applications utilize CDNs for common libraries like AngularJS.</span></span> <span data-ttu-id="22c74-130">您可以從數個 Cdn，像是本節的其中一個參考 AngularJS:</span><span class="sxs-lookup"><span data-stu-id="22c74-130">You can reference AngularJS from one of several CDNs, such as this one:</span></span>

<span data-ttu-id="22c74-131">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Shared/_Layout.cshtml?highlight=10&range=53-67)]</span><span class="sxs-lookup"><span data-stu-id="22c74-131">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Shared/_Layout.cshtml?highlight=10&range=53-67)]</span></span>

<span data-ttu-id="22c74-132">一旦您擁有的參考*angular.js*指令碼檔案，您就可以開始使用 AngularJS web 網頁中。</span><span class="sxs-lookup"><span data-stu-id="22c74-132">Once you have a reference to the *angular.js* script file, you're ready to begin using AngularJS in your web pages.</span></span>

## <a name="key-components"></a><span data-ttu-id="22c74-133">重要元件</span><span class="sxs-lookup"><span data-stu-id="22c74-133">Key components</span></span>

<span data-ttu-id="22c74-134">AngularJS 包含數個主要元件，例如*指示詞*，*範本*，*中繼器*，*模組*， *控制站*，*元件*，*元件路由器*等等。</span><span class="sxs-lookup"><span data-stu-id="22c74-134">AngularJS includes a number of major components, such as *directives*, *templates*, *repeaters*, *modules*, *controllers*, *components*, *component router* and more.</span></span> <span data-ttu-id="22c74-135">讓我們來檢查這些元件合作方式將行為新增至您的網頁。</span><span class="sxs-lookup"><span data-stu-id="22c74-135">Let's examine how these components work together to add behavior to your web pages.</span></span>

### <a name="directives"></a><span data-ttu-id="22c74-136">指示詞</span><span class="sxs-lookup"><span data-stu-id="22c74-136">Directives</span></span>

<span data-ttu-id="22c74-137">使用 AngularJS[指示詞](https://docs.angularjs.org/guide/directive)以 HTML 擴充自訂的屬性和項目。</span><span class="sxs-lookup"><span data-stu-id="22c74-137">AngularJS uses [directives](https://docs.angularjs.org/guide/directive) to extend HTML with custom attributes and elements.</span></span> <span data-ttu-id="22c74-138">AngularJS 指示詞中定義透過`data-ng-*`或`ng-*`前置詞 (`ng`是短的角度)。</span><span class="sxs-lookup"><span data-stu-id="22c74-138">AngularJS directives are defined via `data-ng-*` or `ng-*` prefixes (`ng` is short for angular).</span></span> <span data-ttu-id="22c74-139">有兩種類型的 AngularJS 指示詞：</span><span class="sxs-lookup"><span data-stu-id="22c74-139">There are two types of AngularJS directives:</span></span>

   1. <span data-ttu-id="22c74-140">**基本的指示詞**： 這些預先定義之角度的小組，而 AngularJS 架構的一部分。</span><span class="sxs-lookup"><span data-stu-id="22c74-140">**Primitive Directives**: These are predefined by the Angular team and are part of the AngularJS framework.</span></span>

   2. <span data-ttu-id="22c74-141">**自訂指示詞**： 這些是您可以定義自訂指示詞。</span><span class="sxs-lookup"><span data-stu-id="22c74-141">**Custom Directives**: These are custom directives that you can define.</span></span>

<span data-ttu-id="22c74-142">所有的 AngularJS 應用程式中使用的基本指示詞的其中一個是`ng-app`bootstraps AngularJS 應用程式指示詞。</span><span class="sxs-lookup"><span data-stu-id="22c74-142">One of the primitive directives used in all AngularJS applications is the `ng-app` directive, which bootstraps the AngularJS application.</span></span> <span data-ttu-id="22c74-143">這個指示詞可以套用至`<body>`標記或主體的子項目。</span><span class="sxs-lookup"><span data-stu-id="22c74-143">This directive can be applied to the `<body>` tag or to a child element of the body.</span></span> <span data-ttu-id="22c74-144">我們來看看動作中的範例。</span><span class="sxs-lookup"><span data-stu-id="22c74-144">Let's see an example in action.</span></span> <span data-ttu-id="22c74-145">假設您在 ASP.NET 專案中，您可以加入至 HTML 檔`wwwroot`資料夾，或加入新的控制器動作和相關聯的檢視。</span><span class="sxs-lookup"><span data-stu-id="22c74-145">Assuming you're in an ASP.NET project, you can either add an HTML file to the `wwwroot` folder, or add a new controller action and an associated view.</span></span> <span data-ttu-id="22c74-146">在此情況下，我已將加入新`Directives`至動作方法`HomeController.cs`。</span><span class="sxs-lookup"><span data-stu-id="22c74-146">In this case, I've added a new `Directives` action method to `HomeController.cs`.</span></span> <span data-ttu-id="22c74-147">相關聯的檢視如下所示：</span><span class="sxs-lookup"><span data-stu-id="22c74-147">The associated view is shown here:</span></span>

<span data-ttu-id="22c74-148">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Directives.cshtml?highlight=5,7)]</span><span class="sxs-lookup"><span data-stu-id="22c74-148">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Directives.cshtml?highlight=5,7)]</span></span>

<span data-ttu-id="22c74-149">若要保留這些範例彼此獨立的我不使用共用的版面配置檔案。</span><span class="sxs-lookup"><span data-stu-id="22c74-149">To keep these samples independent of one another, I'm not using the shared layout file.</span></span> <span data-ttu-id="22c74-150">您可以看到我們裝飾與 body 標記`ng-app`指示詞，以指出此頁面是 AngularJS 應用程式。</span><span class="sxs-lookup"><span data-stu-id="22c74-150">You can see that we decorated the body tag with the `ng-app` directive to indicate this page is an AngularJS application.</span></span> <span data-ttu-id="22c74-151">`{{2+2}}`是您將深入了解在不久後的角度的資料繫結運算式。</span><span class="sxs-lookup"><span data-stu-id="22c74-151">The `{{2+2}}` is an Angular data binding expression that you will learn more about in a moment.</span></span> <span data-ttu-id="22c74-152">如果您執行此應用程式，以下是結果：</span><span class="sxs-lookup"><span data-stu-id="22c74-152">Here is the result if you run this application:</span></span>

![簡單的角度指示詞](angular/_static/simple-directive.png)

<span data-ttu-id="22c74-154">AngularJS 中的其他基本指示詞包括：</span><span class="sxs-lookup"><span data-stu-id="22c74-154">Other primitive directives in AngularJS include:</span></span>

<span data-ttu-id="22c74-155">`ng-controller`判斷哪一個 JavaScript 控制站繫結至的檢視。</span><span class="sxs-lookup"><span data-stu-id="22c74-155">`ng-controller` Determines which JavaScript controller is bound to which view.</span></span>

<span data-ttu-id="22c74-156">`ng-model`決定 HTML 元素的屬性的值會繫結的模型。</span><span class="sxs-lookup"><span data-stu-id="22c74-156">`ng-model` Determines the model to which the values of an HTML element's properties are bound.</span></span>

<span data-ttu-id="22c74-157">`ng-init`用來初始化目前範圍的運算式形式的應用程式資料。</span><span class="sxs-lookup"><span data-stu-id="22c74-157">`ng-init` Used to initialize the application data in the form of an expression for the current scope.</span></span>

<span data-ttu-id="22c74-158">`ng-if`移除或重新建立根據提供的運算式 truthiness DOM 中的指定的 HTML 項目。</span><span class="sxs-lookup"><span data-stu-id="22c74-158">`ng-if` Removes or recreates the given HTML element in the DOM based on the truthiness of the expression provided.</span></span>

<span data-ttu-id="22c74-159">`ng-repeat`重複的資料集上指定的區塊的 HTML。</span><span class="sxs-lookup"><span data-stu-id="22c74-159">`ng-repeat` Repeats a given block of HTML over a set of data.</span></span>

<span data-ttu-id="22c74-160">`ng-show`顯示或隱藏指定的 HTML 元素根據提供的運算式。</span><span class="sxs-lookup"><span data-stu-id="22c74-160">`ng-show` Shows or hides the given HTML element based on the expression provided.</span></span>

<span data-ttu-id="22c74-161">如需 AngularJS 中支援的所有基本指示詞的完整清單，請參閱[AngularJS 文件網站上的指示詞的文件章節](https://docs.angularjs.org/api/ng/directive)。</span><span class="sxs-lookup"><span data-stu-id="22c74-161">For a full list of all primitive directives supported in AngularJS, please refer to the [directive documentation section on the AngularJS documentation website](https://docs.angularjs.org/api/ng/directive).</span></span>

### <a name="data-binding"></a><span data-ttu-id="22c74-162">資料繫結</span><span class="sxs-lookup"><span data-stu-id="22c74-162">Data binding</span></span>

<span data-ttu-id="22c74-163">AngularJS 提供[資料繫結](https://docs.angularjs.org/guide/databinding)支援-蜪鎏使用`ng-bind`指示詞或資料繫結運算式語法，例如`{{expression}}`。</span><span class="sxs-lookup"><span data-stu-id="22c74-163">AngularJS provides [data binding](https://docs.angularjs.org/guide/databinding) support out-of-the-box using either the `ng-bind` directive or a data binding expression syntax such as `{{expression}}`.</span></span> <span data-ttu-id="22c74-164">AngularJS 支援如下： 模型中的資料保留在檢視表範本的所有權的同步處理的雙向資料繫結。</span><span class="sxs-lookup"><span data-stu-id="22c74-164">AngularJS supports two-way data binding where data from a model is kept in synchronization with a view template at all times.</span></span> <span data-ttu-id="22c74-165">若要檢視任何變更會自動反映在模型中。</span><span class="sxs-lookup"><span data-stu-id="22c74-165">Any changes to the view are automatically reflected in the model.</span></span> <span data-ttu-id="22c74-166">同樣地，在模型中的任何變更會反映在檢視中。</span><span class="sxs-lookup"><span data-stu-id="22c74-166">Likewise, any changes in the model are reflected in the view.</span></span>

<span data-ttu-id="22c74-167">建立名為伴隨檢視 HTML 檔或控制器動作`Databinding`。</span><span class="sxs-lookup"><span data-stu-id="22c74-167">Create either an HTML file or a controller action with an accompanying view named `Databinding`.</span></span> <span data-ttu-id="22c74-168">在檢視中包含下列設定：</span><span class="sxs-lookup"><span data-stu-id="22c74-168">Include the following in the view:</span></span>

<span data-ttu-id="22c74-169">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Databinding.cshtml?highlight=8,9,10)]</span><span class="sxs-lookup"><span data-stu-id="22c74-169">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Databinding.cshtml?highlight=8,9,10)]</span></span>

<span data-ttu-id="22c74-170">請注意，您可以顯示使用指示詞或資料繫結的模型值 (`ng-bind`)。</span><span class="sxs-lookup"><span data-stu-id="22c74-170">Notice that you can display model values using either directives or data binding (`ng-bind`).</span></span> <span data-ttu-id="22c74-171">結果頁面看起來應該像這樣：</span><span class="sxs-lookup"><span data-stu-id="22c74-171">The resulting page should look like this:</span></span>

![簡單資料繫結](angular/_static/simple-databinding.png)

### <a name="templates"></a><span data-ttu-id="22c74-173">範本</span><span class="sxs-lookup"><span data-stu-id="22c74-173">Templates</span></span>

<span data-ttu-id="22c74-174">[範本](https://docs.angularjs.org/guide/templates)中 AngularJS 無窮 HTML 網頁使用裝飾 AngularJS 指示詞和成品。</span><span class="sxs-lookup"><span data-stu-id="22c74-174">[Templates](https://docs.angularjs.org/guide/templates) in AngularJS are just plain HTML pages decorated with AngularJS directives and artifacts.</span></span> <span data-ttu-id="22c74-175">中的 AngularJS 範本是指示詞、 運算式、 篩選和結合以形成檢視的 HTML 控制項的混合。</span><span class="sxs-lookup"><span data-stu-id="22c74-175">A template in AngularJS is a mixture of directives, expressions, filters, and controls that combine with HTML to form the view.</span></span>

<span data-ttu-id="22c74-176">新增另一個檢視，以示範範本，並加入下列：</span><span class="sxs-lookup"><span data-stu-id="22c74-176">Add another view to demonstrate templates, and add the following to it:</span></span>

<span data-ttu-id="22c74-177">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Templates.cshtml?highlight=8,9,10)]</span><span class="sxs-lookup"><span data-stu-id="22c74-177">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Templates.cshtml?highlight=8,9,10)]</span></span>

<span data-ttu-id="22c74-178">該範本含有 AngularJS 指示詞，像`ng-app`， `ng-init`，`ng-model`和繫結的資料繫結運算式語法`personName`屬性。</span><span class="sxs-lookup"><span data-stu-id="22c74-178">The template has AngularJS directives like `ng-app`, `ng-init`, `ng-model` and data binding expression syntax to bind the `personName` property.</span></span> <span data-ttu-id="22c74-179">在瀏覽器中執行，檢視看起來像下列螢幕擷取畫面：</span><span class="sxs-lookup"><span data-stu-id="22c74-179">Running in the browser, the view looks like the screenshot below:</span></span>

![簡單的範本範例 1](angular/_static/simple-templates-1.png)

<span data-ttu-id="22c74-181">如果您在輸入欄位中輸入變更名稱，即會輸入欄位旁的文字以動態方式更新，顯示角度雙向資料繫結中的動作。</span><span class="sxs-lookup"><span data-stu-id="22c74-181">If you change the name by typing in the input field, you will see the text next to the input field dynamically update, showing Angular two-way data binding in action.</span></span>

![簡單的範本範例 2](angular/_static/simple-templates-2.png)

### <a name="expressions"></a><span data-ttu-id="22c74-183">運算式</span><span class="sxs-lookup"><span data-stu-id="22c74-183">Expressions</span></span>

<span data-ttu-id="22c74-184">[運算式](https://docs.angularjs.org/guide/expression)AngularJS 是在內部撰寫的類似 JavaScript 程式碼片段`{{ expression }}`語法。</span><span class="sxs-lookup"><span data-stu-id="22c74-184">[Expressions](https://docs.angularjs.org/guide/expression) in AngularJS are JavaScript-like code snippets that are written inside the `{{ expression }}` syntax.</span></span> <span data-ttu-id="22c74-185">這些運算式中的資料繫結至 HTML 一樣`ng-bind`指示詞。</span><span class="sxs-lookup"><span data-stu-id="22c74-185">The data from these expressions is bound to HTML the same way as `ng-bind` directives.</span></span> <span data-ttu-id="22c74-186">AngularJS 運算式和 JavaScript 的規則運算式的主要差別在於運算式會評估該 AngularJS `$scope` AngularJS 中的物件。</span><span class="sxs-lookup"><span data-stu-id="22c74-186">The main difference between AngularJS expressions and regular JavaScript expressions is that AngularJS expressions are evaluated against the `$scope` object in AngularJS.</span></span>

<span data-ttu-id="22c74-187">下列繫結的範例中的 AngularJS 運算式`personName`而且簡單 JavaScript 計算運算式：</span><span class="sxs-lookup"><span data-stu-id="22c74-187">The AngularJS expressions in the sample below bind `personName` and a simple JavaScript calculated expression:</span></span>

<span data-ttu-id="22c74-188">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Expressions.cshtml?highlight=8,9,10)]</span><span class="sxs-lookup"><span data-stu-id="22c74-188">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Expressions.cshtml?highlight=8,9,10)]</span></span>

<span data-ttu-id="22c74-189">在瀏覽器顯示執行此範例`personName`資料和計算的結果：</span><span class="sxs-lookup"><span data-stu-id="22c74-189">The example running in the browser displays the `personName` data and the results of the calculation:</span></span>

![簡單運算式](angular/_static/simple-expressions.png)

### <a name="repeaters"></a><span data-ttu-id="22c74-191">重複項</span><span class="sxs-lookup"><span data-stu-id="22c74-191">Repeaters</span></span>

<span data-ttu-id="22c74-192">透過呼叫的基本指示詞在 AngularJS 重複進行`ng-repeat`。</span><span class="sxs-lookup"><span data-stu-id="22c74-192">Repeating in AngularJS is done via a primitive directive called `ng-repeat`.</span></span> <span data-ttu-id="22c74-193">`ng-repeat`指示詞會重複的資料陣列的長度對重複在檢視中指定的 HTML 項目。</span><span class="sxs-lookup"><span data-stu-id="22c74-193">The `ng-repeat` directive repeats a given HTML element in a view over the length of a repeating data array.</span></span> <span data-ttu-id="22c74-194">中繼器 AngularJS 中的可以重複透過字串或物件的陣列。</span><span class="sxs-lookup"><span data-stu-id="22c74-194">Repeaters in AngularJS can repeat over an array of strings or objects.</span></span> <span data-ttu-id="22c74-195">以下是重複的字串陣列進行反覆的範例使用方式：</span><span class="sxs-lookup"><span data-stu-id="22c74-195">Here is a sample usage of repeating over an array of strings:</span></span>

<span data-ttu-id="22c74-196">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Repeaters.cshtml?highlight=8,10,11)]</span><span class="sxs-lookup"><span data-stu-id="22c74-196">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Repeaters.cshtml?highlight=8,10,11)]</span></span>

<span data-ttu-id="22c74-197">[Repeat 指示詞](https://docs.angularjs.org/api/ng/directive/ngRepeat)會輸出一系列中的未排序的清單，清單項目，為您可以在這個螢幕擷取畫面所示的開發人員工具中看到：</span><span class="sxs-lookup"><span data-stu-id="22c74-197">The [repeat directive](https://docs.angularjs.org/api/ng/directive/ngRepeat) outputs a series of list items in an unordered list, as you can see in the developer tools shown in this screenshot:</span></span>

![中繼器範例](angular/_static/repeater.png)

<span data-ttu-id="22c74-199">以下是對物件的陣列，重複的範例。</span><span class="sxs-lookup"><span data-stu-id="22c74-199">Here is an example that repeats over an array of objects.</span></span> <span data-ttu-id="22c74-200">`ng-init`指示詞建立`names`陣列，其中每個項目是第一次包含的物件，而姓氏。</span><span class="sxs-lookup"><span data-stu-id="22c74-200">The `ng-init` directive establishes a `names` array, where each element is an object containing first and last names.</span></span> <span data-ttu-id="22c74-201">`ng-repeat`指派、 `name in names`，輸出每個陣列元素的清單項目。</span><span class="sxs-lookup"><span data-stu-id="22c74-201">The `ng-repeat` assignment, `name in names`, outputs a list item for every array element.</span></span>

<span data-ttu-id="22c74-202">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Repeaters2.cshtml?highlight=8,9,10,11,13,14)]</span><span class="sxs-lookup"><span data-stu-id="22c74-202">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Repeaters2.cshtml?highlight=8,9,10,11,13,14)]</span></span>

<span data-ttu-id="22c74-203">在此情況下，輸出是與前面範例相同。</span><span class="sxs-lookup"><span data-stu-id="22c74-203">The output in this case is the same as in the previous example.</span></span>

<span data-ttu-id="22c74-204">角度提供一些其他指示詞，可協助提供根據位置迴圈在其執行中的行為。</span><span class="sxs-lookup"><span data-stu-id="22c74-204">Angular provides some additional directives that can help provide behavior based on where the loop is in its execution.</span></span>

`$index`

<span data-ttu-id="22c74-205">使用`$index`中`ng-repeat`迴圈，以判定哪一個索引位置您迴圈目前位於上。</span><span class="sxs-lookup"><span data-stu-id="22c74-205">Use `$index` in the `ng-repeat` loop to determine which index position your loop currently is on.</span></span>

<span data-ttu-id="22c74-206">`$even` 和 `$odd`</span><span class="sxs-lookup"><span data-stu-id="22c74-206">`$even` and `$odd`</span></span>

<span data-ttu-id="22c74-207">使用`$even`中`ng-repeat`迴圈，以判斷目前的索引，在迴圈中是否即使索引的資料列。</span><span class="sxs-lookup"><span data-stu-id="22c74-207">Use `$even` in the `ng-repeat` loop to determine whether the current index in your loop is an even indexed row.</span></span> <span data-ttu-id="22c74-208">同樣地，使用`$odd`判斷目前的索引是否為奇數的索引資料列。</span><span class="sxs-lookup"><span data-stu-id="22c74-208">Similarly, use `$odd` to determine if the current index is an odd indexed row.</span></span>

<span data-ttu-id="22c74-209">`$first` 和 `$last`</span><span class="sxs-lookup"><span data-stu-id="22c74-209">`$first` and `$last`</span></span>

<span data-ttu-id="22c74-210">使用`$first`中`ng-repeat`迴圈，以判斷第一個資料列是否包含在迴圈中目前的索引。</span><span class="sxs-lookup"><span data-stu-id="22c74-210">Use `$first` in the `ng-repeat` loop to determine whether the current index in your loop is the first row.</span></span> <span data-ttu-id="22c74-211">同樣地，使用`$last`判斷目前的索引是否為最後一個資料列。</span><span class="sxs-lookup"><span data-stu-id="22c74-211">Similarly, use `$last` to determine if the current index is the last row.</span></span>

<span data-ttu-id="22c74-212">以下是範例，示範`$index`， `$even`， `$odd`， `$first`，和`$last`動作：</span><span class="sxs-lookup"><span data-stu-id="22c74-212">Below is a sample that shows `$index`, `$even`, `$odd`, `$first`, and `$last` in action:</span></span>

<span data-ttu-id="22c74-213">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Repeaters3.cshtml?highlight=14,15,16,17,18)]</span><span class="sxs-lookup"><span data-stu-id="22c74-213">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Repeaters3.cshtml?highlight=14,15,16,17,18)]</span></span>

<span data-ttu-id="22c74-214">以下是產生的輸出：</span><span class="sxs-lookup"><span data-stu-id="22c74-214">Here is the resulting output:</span></span>

![中繼器範例 2](angular/_static/repeaters2.png)

### <a name="scope"></a><span data-ttu-id="22c74-216">$scope</span><span class="sxs-lookup"><span data-stu-id="22c74-216">$scope</span></span>

<span data-ttu-id="22c74-217">`$scope`是 JavaScript 物件，可做為黏附 （範本） 檢視和控制器 （如下所述） 之間。</span><span class="sxs-lookup"><span data-stu-id="22c74-217">`$scope` is a JavaScript object that acts as glue between the view (template) and the controller (explained below).</span></span> <span data-ttu-id="22c74-218">檢視中的範本 AngularJS 只知道附加到數值`$scope`控制器中的物件。</span><span class="sxs-lookup"><span data-stu-id="22c74-218">A view template in AngularJS only knows about the values attached to the `$scope` object in the controller.</span></span>

> [!NOTE]
> <span data-ttu-id="22c74-219">MVVM 世界`$scope`AngularJS 中的物件通常會定義為 ViewModel。</span><span class="sxs-lookup"><span data-stu-id="22c74-219">In the MVVM world, the `$scope` object in AngularJS is often defined as the ViewModel.</span></span> <span data-ttu-id="22c74-220">AngularJS 小組指`$scope`物件做為資料模型。</span><span class="sxs-lookup"><span data-stu-id="22c74-220">The AngularJS team refers to the `$scope` object as the Data-Model.</span></span> <span data-ttu-id="22c74-221">[深入了解範圍中 AngularJS](https://docs.angularjs.org/guide/scope)。</span><span class="sxs-lookup"><span data-stu-id="22c74-221">[Learn more about Scopes in AngularJS](https://docs.angularjs.org/guide/scope).</span></span>

<span data-ttu-id="22c74-222">以下是簡單的範例示範如何設定屬性`$scope`在個別的 JavaScript 檔案中， *scope.js*:</span><span class="sxs-lookup"><span data-stu-id="22c74-222">Below is a simple example showing how to set properties on `$scope` within a separate JavaScript file, *scope.js*:</span></span>

<span data-ttu-id="22c74-223">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/scope.js?highlight=2,3)]</span><span class="sxs-lookup"><span data-stu-id="22c74-223">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/scope.js?highlight=2,3)]</span></span>

<span data-ttu-id="22c74-224">觀察`$scope`參數傳遞至控制器，第 2 行上。</span><span class="sxs-lookup"><span data-stu-id="22c74-224">Observe the `$scope` parameter passed to the controller on line 2.</span></span> <span data-ttu-id="22c74-225">這個物件是檢視的知道。</span><span class="sxs-lookup"><span data-stu-id="22c74-225">This object is what the view knows about.</span></span> <span data-ttu-id="22c74-226">在行 3，我們會設定名為"name"到"Mary Jane"的屬性。</span><span class="sxs-lookup"><span data-stu-id="22c74-226">On line 3, we are setting a property called "name" to "Mary Jane".</span></span>

<span data-ttu-id="22c74-227">由檢視找不到特定的屬性時，發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="22c74-227">What happens when a particular property is not found by the view?</span></span> <span data-ttu-id="22c74-228">下面定義的檢視是指"name"和"age"屬性：</span><span class="sxs-lookup"><span data-stu-id="22c74-228">The view defined below refers to "name" and "age" properties:</span></span>

<span data-ttu-id="22c74-229">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Scope.cshtml?highlight=9,10,14)]</span><span class="sxs-lookup"><span data-stu-id="22c74-229">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Scope.cshtml?highlight=9,10,14)]</span></span>

<span data-ttu-id="22c74-230">請注意第 9 我們要求要顯示 「 名稱 」 屬性使用運算式語法 Angular 行。</span><span class="sxs-lookup"><span data-stu-id="22c74-230">Notice on line 9 that we are asking Angular to show the "name" property using expression syntax.</span></span> <span data-ttu-id="22c74-231">第 10 行然後是指"age"，不存在的屬性。</span><span class="sxs-lookup"><span data-stu-id="22c74-231">Line 10 then refers to "age", a property that does not exist.</span></span> <span data-ttu-id="22c74-232">執行中範例顯示天數設為"Mary Jane"和執行任何動作的名稱。</span><span class="sxs-lookup"><span data-stu-id="22c74-232">The running example shows the name set to "Mary Jane" and nothing for age.</span></span> <span data-ttu-id="22c74-233">會忽略遺漏的屬性。</span><span class="sxs-lookup"><span data-stu-id="22c74-233">Missing properties are ignored.</span></span>

![範圍範例](angular/_static/scope.png)

### <a name="modules"></a><span data-ttu-id="22c74-235">模組</span><span class="sxs-lookup"><span data-stu-id="22c74-235">Modules</span></span>

<span data-ttu-id="22c74-236">A[模組](https://docs.angularjs.org/guide/module)在 AngularJS 是集合的控制站、 服務、 指示詞等等。`angular.module()`函式呼叫用來建立、 註冊及擷取中 AngularJS 模組。</span><span class="sxs-lookup"><span data-stu-id="22c74-236">A [module](https://docs.angularjs.org/guide/module) in AngularJS is a collection of controllers, services, directives, etc. The `angular.module()` function call is used to create, register, and retrieve modules in AngularJS.</span></span> <span data-ttu-id="22c74-237">所有模組，包括隨附的 AngularJS 小組與第三方廠商程式庫，應該使用都註冊`angular.module()`函式。</span><span class="sxs-lookup"><span data-stu-id="22c74-237">All modules, including those shipped by the AngularJS team and third party libraries, should be registered using the `angular.module()` function.</span></span>

<span data-ttu-id="22c74-238">以下是示範如何建立新的模組 AngularJS 中的程式碼的程式碼片段。</span><span class="sxs-lookup"><span data-stu-id="22c74-238">Below is a snippet of code that shows how to create a new module in AngularJS.</span></span> <span data-ttu-id="22c74-239">第一個參數是模組的名稱。</span><span class="sxs-lookup"><span data-stu-id="22c74-239">The first parameter is the name of the module.</span></span> <span data-ttu-id="22c74-240">第二個參數會定義在其他模組相依性。</span><span class="sxs-lookup"><span data-stu-id="22c74-240">The second parameter defines dependencies on other modules.</span></span> <span data-ttu-id="22c74-241">在本文中，稍後我們將會顯示如何將這些相依性才能傳遞`angular.module()`方法呼叫。</span><span class="sxs-lookup"><span data-stu-id="22c74-241">Later in this article, we will be showing how to pass these dependencies to an `angular.module()` method call.</span></span>

```javascript
var personApp = angular.module('personApp', []);
```

<span data-ttu-id="22c74-242">使用`ng-app`代表頁面上的 AngularJS 模組的指示詞。</span><span class="sxs-lookup"><span data-stu-id="22c74-242">Use the `ng-app` directive to represent an AngularJS module on the page.</span></span> <span data-ttu-id="22c74-243">若要使用模組，請指定模組名稱`personApp`在此範例中，以`ng-app`我們範本指示詞。</span><span class="sxs-lookup"><span data-stu-id="22c74-243">To use a module, assign the name of the module, `personApp` in this example, to the `ng-app` directive in our template.</span></span>

```html
<body ng-app="personApp">
```

### <a name="controllers"></a><span data-ttu-id="22c74-244">控制站</span><span class="sxs-lookup"><span data-stu-id="22c74-244">Controllers</span></span>

<span data-ttu-id="22c74-245">[控制站](https://docs.angularjs.org/guide/controller)AngularJS 是第一個程式碼的進入點。</span><span class="sxs-lookup"><span data-stu-id="22c74-245">[Controllers](https://docs.angularjs.org/guide/controller) in AngularJS are the first point of entry for your code.</span></span> <span data-ttu-id="22c74-246">`<module name>.controller()`函式呼叫用來建立及註冊中 AngularJS 控制器。</span><span class="sxs-lookup"><span data-stu-id="22c74-246">The `<module name>.controller()` function call is used to create and register controllers in AngularJS.</span></span> <span data-ttu-id="22c74-247">`ng-controller`指示詞用來表示 HTML 網頁上的 AngularJS 控制器。</span><span class="sxs-lookup"><span data-stu-id="22c74-247">The `ng-controller` directive is used to represent an AngularJS controller on the HTML page.</span></span> <span data-ttu-id="22c74-248">若要設定狀態和資料模型的行為是 Angular 控制站的角色 (`$scope`)。</span><span class="sxs-lookup"><span data-stu-id="22c74-248">The role of the controller in Angular is to set state and behavior of the data model (`$scope`).</span></span> <span data-ttu-id="22c74-249">控制站不應該用於直接操作的 DOM。</span><span class="sxs-lookup"><span data-stu-id="22c74-249">Controllers should not be used to manipulate the DOM directly.</span></span>

<span data-ttu-id="22c74-250">以下是註冊新的控制站的程式碼的程式碼片段。</span><span class="sxs-lookup"><span data-stu-id="22c74-250">Below is a snippet of code that registers a new controller.</span></span> <span data-ttu-id="22c74-251">`personApp`片段中的變數參考一個角度的模組，請在第 2 行定義。</span><span class="sxs-lookup"><span data-stu-id="22c74-251">The `personApp` variable in the snippet references an Angular module, which is defined on line 2.</span></span>

<span data-ttu-id="22c74-252">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/controllers.js?highlight=2,5)]</span><span class="sxs-lookup"><span data-stu-id="22c74-252">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/controllers.js?highlight=2,5)]</span></span>

<span data-ttu-id="22c74-253">檢視使用`ng-controller`指示詞指定的控制器名稱：</span><span class="sxs-lookup"><span data-stu-id="22c74-253">The view using the `ng-controller` directive assigns the controller name:</span></span>

<span data-ttu-id="22c74-254">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Controllers.cshtml?highlight=8,14)]</span><span class="sxs-lookup"><span data-stu-id="22c74-254">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Controllers.cshtml?highlight=8,14)]</span></span>

<span data-ttu-id="22c74-255">頁面會顯示 「 Mary"和"Jane"對應至`firstName`和`lastName`屬性附加至`$scope`物件：</span><span class="sxs-lookup"><span data-stu-id="22c74-255">The page shows "Mary" and "Jane" that correspond to the `firstName` and `lastName` properties attached to the `$scope` object:</span></span>

![控制站範例](angular/_static/controllers.png)

### <a name="components"></a><span data-ttu-id="22c74-257">元件</span><span class="sxs-lookup"><span data-stu-id="22c74-257">Components</span></span>

<span data-ttu-id="22c74-258">[元件](https://docs.angularjs.org/guide/component)中 Angular 1.5.x 允許封裝及建立個別的 HTML 元素的能力。</span><span class="sxs-lookup"><span data-stu-id="22c74-258">[Components](https://docs.angularjs.org/guide/component) in Angular 1.5.x allow for the encapsulation and capability of creating individual HTML elements.</span></span> <span data-ttu-id="22c74-259">您無法在角度 1.4.x 能夠達到使用.directive() 方法相同的功能。</span><span class="sxs-lookup"><span data-stu-id="22c74-259">In Angular 1.4.x you could achieve the same feature using the .directive() method.</span></span>

<span data-ttu-id="22c74-260">使用.component() 方法，開發已經過簡化獲得指示詞和控制器的功能。</span><span class="sxs-lookup"><span data-stu-id="22c74-260">By using the .component() method, development is simplified gaining the functionality of the directive and the controller.</span></span> <span data-ttu-id="22c74-261">其他優點包括：範圍隔離固有的最佳作法，並移轉至角度 2 變得更容易的工作。</span><span class="sxs-lookup"><span data-stu-id="22c74-261">Other benefits include; scope isolation, best practices are inherent, and migration to Angular 2 becomes an easier task.</span></span> <span data-ttu-id="22c74-262">`<module name>.component()`函式呼叫用來建立及註冊 AngularJS 中的元件。</span><span class="sxs-lookup"><span data-stu-id="22c74-262">The `<module name>.component()` function call is used to create and register components in AngularJS.</span></span>

<span data-ttu-id="22c74-263">以下是註冊的新元件的程式碼的程式碼片段。</span><span class="sxs-lookup"><span data-stu-id="22c74-263">Below is a snippet of code that registers a new component.</span></span> <span data-ttu-id="22c74-264">`personApp`片段中的變數參考一個角度的模組，請在第 2 行定義。</span><span class="sxs-lookup"><span data-stu-id="22c74-264">The `personApp` variable in the snippet references an Angular module, which is defined on line 2.</span></span>

<span data-ttu-id="22c74-265">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/components.js?highlight=2,5,13)]</span><span class="sxs-lookup"><span data-stu-id="22c74-265">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/components.js?highlight=2,5,13)]</span></span>

<span data-ttu-id="22c74-266">檢視，我們要在其中顯示的自訂 HTML 項目。</span><span class="sxs-lookup"><span data-stu-id="22c74-266">The view where we are displaying the custom HTML element.</span></span>

<span data-ttu-id="22c74-267">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Components.cshtml?highlight=8)]</span><span class="sxs-lookup"><span data-stu-id="22c74-267">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/Home/Components.cshtml?highlight=8)]</span></span>

<span data-ttu-id="22c74-268">相關聯的範本，供元件使用：</span><span class="sxs-lookup"><span data-stu-id="22c74-268">The associated template used by component:</span></span>

<span data-ttu-id="22c74-269">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/partials/personcomponent.html?highlight=2,3)]</span><span class="sxs-lookup"><span data-stu-id="22c74-269">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/partials/personcomponent.html?highlight=2,3)]</span></span>

<span data-ttu-id="22c74-270">頁面會顯示 「 Aftab"和"Ansari"對應至`firstName`和`lastName`屬性附加至`vm`物件：</span><span class="sxs-lookup"><span data-stu-id="22c74-270">The page shows "Aftab" and "Ansari" that correspond to the `firstName` and `lastName` properties attached to the `vm` object:</span></span>

![元件範例](angular/_static/components.png)

### <a name="services"></a><span data-ttu-id="22c74-272">服務</span><span class="sxs-lookup"><span data-stu-id="22c74-272">Services</span></span>

<span data-ttu-id="22c74-273">[服務](https://docs.angularjs.org/guide/services)AngularJS 中常用的抽象成可在整個存留期角度的應用程式檔案的共用程式碼。</span><span class="sxs-lookup"><span data-stu-id="22c74-273">[Services](https://docs.angularjs.org/guide/services) in AngularJS are commonly used for shared code that is abstracted away into a file which can be used throughout the lifetime of an Angular application.</span></span> <span data-ttu-id="22c74-274">服務會延遲的方式具現化，這表示，將不會服務的執行個體，除非使用依存於服務的元件。</span><span class="sxs-lookup"><span data-stu-id="22c74-274">Services are lazily instantiated, meaning that there will not be an instance of a service unless a component that depends on the service gets used.</span></span> <span data-ttu-id="22c74-275">處理站會使用 AngularJS 應用程式的服務的範例。</span><span class="sxs-lookup"><span data-stu-id="22c74-275">Factories are an example of a service used in AngularJS applications.</span></span> <span data-ttu-id="22c74-276">使用建立處理站`myApp.factory()`函式呼叫，其中`myApp`是模組。</span><span class="sxs-lookup"><span data-stu-id="22c74-276">Factories are created using the `myApp.factory()` function call, where `myApp` is the module.</span></span>

<span data-ttu-id="22c74-277">以下是示範如何使用中的 AngularJS 處理站的範例：</span><span class="sxs-lookup"><span data-stu-id="22c74-277">Below is an example that shows how to use factories in AngularJS:</span></span>

<span data-ttu-id="22c74-278">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/simpleFactory.js?highlight=1)]</span><span class="sxs-lookup"><span data-stu-id="22c74-278">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/simpleFactory.js?highlight=1)]</span></span>

<span data-ttu-id="22c74-279">若要從控制器中呼叫此處理站，請傳遞`personFactory`當做參數`controller`函式：</span><span class="sxs-lookup"><span data-stu-id="22c74-279">To call this factory from the controller, pass `personFactory` as a parameter to the `controller` function:</span></span>

```javascript
personApp.controller('personController', function($scope,personFactory) {
  $scope.name = personFactory.getName();
});
```

### <a name="using-services-to-talk-to-a-rest-endpoint"></a><span data-ttu-id="22c74-280">使用與 REST 端點通訊的服務</span><span class="sxs-lookup"><span data-stu-id="22c74-280">Using services to talk to a REST endpoint</span></span>

<span data-ttu-id="22c74-281">以下是端對端範例使用服務中 AngularJS 與 ASP.NET Core Web API 端點互動。</span><span class="sxs-lookup"><span data-stu-id="22c74-281">Below is an end-to-end example using services in AngularJS to interact with an ASP.NET Core Web API endpoint.</span></span> <span data-ttu-id="22c74-282">範例會從 Web API 取得資料，並檢視範本中顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="22c74-282">The example gets data from the Web API and displays the data in a view template.</span></span> <span data-ttu-id="22c74-283">讓我們先開始進行檢視：</span><span class="sxs-lookup"><span data-stu-id="22c74-283">Let's start with the view first:</span></span>

<span data-ttu-id="22c74-284">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/People/Index.cshtml?highlight=5,8,10,17,18,19)]</span><span class="sxs-lookup"><span data-stu-id="22c74-284">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/People/Index.cshtml?highlight=5,8,10,17,18,19)]</span></span>

<span data-ttu-id="22c74-285">在此檢視中，我們有 Angular 模組呼叫`PersonsApp`和控制器呼叫`personController`。</span><span class="sxs-lookup"><span data-stu-id="22c74-285">In this view, we have an Angular module called `PersonsApp` and a controller called `personController`.</span></span> <span data-ttu-id="22c74-286">我們使用`ng-repeat`來反覆查看的人員清單。</span><span class="sxs-lookup"><span data-stu-id="22c74-286">We are using `ng-repeat` to iterate over the list of persons.</span></span> <span data-ttu-id="22c74-287">我們正在參考 17-19 版的程式行的三個自訂 JavaScript 檔案。</span><span class="sxs-lookup"><span data-stu-id="22c74-287">We are referencing three custom JavaScript files on lines 17-19.</span></span>

<span data-ttu-id="22c74-288">*PersonApp.js*檔案用來註冊`PersonsApp`模組; 以及的語法是類似於先前的範例。</span><span class="sxs-lookup"><span data-stu-id="22c74-288">The *personApp.js* file is used to register the `PersonsApp` module; and, the syntax is similar to previous examples.</span></span> <span data-ttu-id="22c74-289">我們使用`angular.module`函式來建立新的執行個體，我們將使用的模組。</span><span class="sxs-lookup"><span data-stu-id="22c74-289">We are using the `angular.module` function to create a new instance of the module that we will be working with.</span></span>

<span data-ttu-id="22c74-290">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personApp.js?highlight=3)]</span><span class="sxs-lookup"><span data-stu-id="22c74-290">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personApp.js?highlight=3)]</span></span>

<span data-ttu-id="22c74-291">讓我們看看*personFactory.js*底下。</span><span class="sxs-lookup"><span data-stu-id="22c74-291">Let's take a look at *personFactory.js*, below.</span></span> <span data-ttu-id="22c74-292">我們正在撥打的模組`factory`方法來建立處理站。</span><span class="sxs-lookup"><span data-stu-id="22c74-292">We are calling the module’s `factory` method to create a factory.</span></span> <span data-ttu-id="22c74-293">第 12 顯示內建 Angular`$http`從 web 服務擷取使用者資訊的服務。</span><span class="sxs-lookup"><span data-stu-id="22c74-293">Line 12 shows the built-in Angular `$http` service retrieving people information from a web service.</span></span>

<span data-ttu-id="22c74-294">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personFactory.js?highlight=6,7,12)]</span><span class="sxs-lookup"><span data-stu-id="22c74-294">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personFactory.js?highlight=6,7,12)]</span></span>

<span data-ttu-id="22c74-295">在*personController.js*，我們正在撥打的模組`controller`方法來建立控制器。</span><span class="sxs-lookup"><span data-stu-id="22c74-295">In *personController.js*, we are calling the module’s `controller` method to create the controller.</span></span> <span data-ttu-id="22c74-296">`$scope`物件的`people`personFactory （行 13） 從傳回的資料指派給屬性。</span><span class="sxs-lookup"><span data-stu-id="22c74-296">The `$scope` object's `people` property is assigned the data returned from the personFactory (line 13).</span></span>

<span data-ttu-id="22c74-297">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personController.js?highlight=6,7,13)]</span><span class="sxs-lookup"><span data-stu-id="22c74-297">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personController.js?highlight=6,7,13)]</span></span>

<span data-ttu-id="22c74-298">讓我們快速查看 Web 應用程式開發介面和其背後的模型。</span><span class="sxs-lookup"><span data-stu-id="22c74-298">Let's take a quick look at the Web API and the model behind it.</span></span> <span data-ttu-id="22c74-299">`Person`模型是 POCO （純舊 CLR 物件） 使用`Id`， `FirstName`，和`LastName`屬性：</span><span class="sxs-lookup"><span data-stu-id="22c74-299">The `Person` model is a POCO (Plain Old CLR Object) with `Id`, `FirstName`, and `LastName` properties:</span></span>

<span data-ttu-id="22c74-300">[!code-csharp[Main](angular/sample/AngularJSSample/src/AngularJSSample/Models/Person.cs)]</span><span class="sxs-lookup"><span data-stu-id="22c74-300">[!code-csharp[Main](angular/sample/AngularJSSample/src/AngularJSSample/Models/Person.cs)]</span></span>

<span data-ttu-id="22c74-301">`Person`控制站會傳回 JSON 格式的清單`Person`物件：</span><span class="sxs-lookup"><span data-stu-id="22c74-301">The `Person` controller returns a JSON-formatted list of `Person` objects:</span></span>

<span data-ttu-id="22c74-302">[!code-csharp[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Controllers/Api/PersonController.cs?highlight=9,10,19)]</span><span class="sxs-lookup"><span data-stu-id="22c74-302">[!code-csharp[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Controllers/Api/PersonController.cs?highlight=9,10,19)]</span></span>

<span data-ttu-id="22c74-303">我們來看看應用程式執行動作：</span><span class="sxs-lookup"><span data-stu-id="22c74-303">Let's see the application in action:</span></span>

![結果顯示其餘的控制器](angular/_static/rest-bound.png)

<span data-ttu-id="22c74-305">您可以[檢視 GitHub 上的應用程式的結構](https://github.com/aspnet/Docs/tree/master/aspnetcore/client-side/angular/sample)。</span><span class="sxs-lookup"><span data-stu-id="22c74-305">You can [view the application's structure on GitHub](https://github.com/aspnet/Docs/tree/master/aspnetcore/client-side/angular/sample).</span></span>

> [!NOTE]
> <span data-ttu-id="22c74-306">如需建構 AngularJS 應用程式的相關詳細資訊，請參閱[John Papa 角度樣式指南](https://github.com/johnpapa/angular-styleguide)</span><span class="sxs-lookup"><span data-stu-id="22c74-306">For more on structuring AngularJS applications, see [John Papa's Angular Style Guide](https://github.com/johnpapa/angular-styleguide)</span></span>

&nbsp;

> [!NOTE]
> <span data-ttu-id="22c74-307">若要建立 AngularJS 模組、 控制器、 處理站，指示詞和檢視檔案輕鬆地，請務必簽出 Sayed Hashimi [SideWaffle 範本組件適用於 Visual Studio](http://sidewaffle.com/)。</span><span class="sxs-lookup"><span data-stu-id="22c74-307">To create AngularJS module, controller, factory, directive and view files easily, be sure to check out Sayed Hashimi's [SideWaffle template pack for Visual Studio](http://sidewaffle.com/).</span></span> <span data-ttu-id="22c74-308">Sayed Hashimi 是 Visual Studio Web 小組，microsoft 資深程式管理員和 SideWaffle 範本會被視為金級標準。</span><span class="sxs-lookup"><span data-stu-id="22c74-308">Sayed Hashimi is a Senior Program Manager on the Visual Studio Web Team at Microsoft and SideWaffle templates are considered the gold standard.</span></span> <span data-ttu-id="22c74-309">在撰寫本文時，SideWaffle 適用於 Visual Studio 2012、 2013年和 2015年。</span><span class="sxs-lookup"><span data-stu-id="22c74-309">At the time of this writing, SideWaffle is available for Visual Studio 2012, 2013, and 2015.</span></span>

### <a name="routing-and-multiple-views"></a><span data-ttu-id="22c74-310">路由和多個檢視</span><span class="sxs-lookup"><span data-stu-id="22c74-310">Routing and multiple views</span></span>

<span data-ttu-id="22c74-311">AngularJS 有內建路由提供者來處理 SPA （單一頁面應用程式），以瀏覽。</span><span class="sxs-lookup"><span data-stu-id="22c74-311">AngularJS has a built-in route provider to handle SPA (Single Page Application) based navigation.</span></span> <span data-ttu-id="22c74-312">若要使用 AngularJS 中的路由，您必須新增`angular-route`使用 Bower 的程式庫。</span><span class="sxs-lookup"><span data-stu-id="22c74-312">To work with routing in AngularJS, you must add the `angular-route` library using Bower.</span></span> <span data-ttu-id="22c74-313">您可以看到在[bower.json](#angular-bower-json)開頭本文，我們已參考它的受測專案的參考檔案。</span><span class="sxs-lookup"><span data-stu-id="22c74-313">You can see in the [bower.json](#angular-bower-json) file referenced at the start of this article that we are already referencing it in our project.</span></span>

<span data-ttu-id="22c74-314">安裝封裝之後，加入指令碼參考 (*角度 route.js*) 至您的檢視。</span><span class="sxs-lookup"><span data-stu-id="22c74-314">After you install the package, add the script reference (*angular-route.js*) to your view.</span></span>

<span data-ttu-id="22c74-315">現在讓我們來看我們有建置，並瀏覽加入個人應用程式。</span><span class="sxs-lookup"><span data-stu-id="22c74-315">Now let's take the Person App we have been building and add navigation to it.</span></span> <span data-ttu-id="22c74-316">首先，我們將複製的應用程式來建立新`PeopleController`呼叫動作`Spa`和對應`Spa.cshtml`藉由複製 Index.cshtml 檢視中的檢視`People`資料夾。</span><span class="sxs-lookup"><span data-stu-id="22c74-316">First, we will make a copy of the app by creating a new `PeopleController` action called `Spa` and a corresponding `Spa.cshtml` view by copying the Index.cshtml view in the `People` folder.</span></span> <span data-ttu-id="22c74-317">加入指令碼參考`angular-route`（請參閱第 11 行）。</span><span class="sxs-lookup"><span data-stu-id="22c74-317">Add a script reference to `angular-route` (see line 11).</span></span> <span data-ttu-id="22c74-318">也新增`div`標示`ng-view`指示詞 （請參閱第 6 行） 做為將檢視中的預留位置。</span><span class="sxs-lookup"><span data-stu-id="22c74-318">Also add a `div` marked with the `ng-view` directive (see line 6) as a placeholder to place views in.</span></span> <span data-ttu-id="22c74-319">我們將會使用數個其他*.js* 13-16 的程式行所參考的檔案。</span><span class="sxs-lookup"><span data-stu-id="22c74-319">We are going to be using several additional *.js* files which are referenced on lines 13-16.</span></span>

<span data-ttu-id="22c74-320">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/People/Spa.cshtml?highlight=6,11,12,13,14,15,16)]</span><span class="sxs-lookup"><span data-stu-id="22c74-320">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/People/Spa.cshtml?highlight=6,11,12,13,14,15,16)]</span></span>

<span data-ttu-id="22c74-321">讓我們看看*personModule.js*檔案以查看如何我們會執行個體化路由模組。</span><span class="sxs-lookup"><span data-stu-id="22c74-321">Let's take a look at *personModule.js* file to see how we are instantiating the module with routing.</span></span> <span data-ttu-id="22c74-322">我們傳遞`ngRoute`做為程式庫的模組。</span><span class="sxs-lookup"><span data-stu-id="22c74-322">We are passing `ngRoute` as a library into the module.</span></span> <span data-ttu-id="22c74-323">此模組會處理路由在我們的應用程式。</span><span class="sxs-lookup"><span data-stu-id="22c74-323">This module handles routing in our application.</span></span>

<span data-ttu-id="22c74-324">[!code-javascript[Main](angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personModule.js)]</span><span class="sxs-lookup"><span data-stu-id="22c74-324">[!code-javascript[Main](angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personModule.js)]</span></span>

<span data-ttu-id="22c74-325">*PersonRoutes.js*檔案中下, 面定義的路由提供者為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="22c74-325">The *personRoutes.js* file, below, defines routes based on the route provider.</span></span> <span data-ttu-id="22c74-326">行 4-7 定義所有效地說，當使用的 URL 巡覽`/persons`是要求，請使用範本，呼叫`partials/personlist`工作透過`personListController`。</span><span class="sxs-lookup"><span data-stu-id="22c74-326">Lines 4-7 define navigation by effectively saying, when a URL with `/persons` is requested, use a template called `partials/personlist` by working through `personListController`.</span></span> <span data-ttu-id="22c74-327">線條 8-11 表示使用路由參數的詳細資料頁面`personId`。</span><span class="sxs-lookup"><span data-stu-id="22c74-327">Lines 8-11 indicate a detail page with a route parameter of `personId`.</span></span> <span data-ttu-id="22c74-328">如果 URL 不符合的模式之一，Angular 會預設為`/persons`檢視。</span><span class="sxs-lookup"><span data-stu-id="22c74-328">If the URL doesn't match one of the patterns, Angular defaults to the `/persons` view.</span></span>

<span data-ttu-id="22c74-329">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personRoutes.js?highlight=4,5,6,7,8,9,10,11,13)]</span><span class="sxs-lookup"><span data-stu-id="22c74-329">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personRoutes.js?highlight=4,5,6,7,8,9,10,11,13)]</span></span>

<span data-ttu-id="22c74-330">`personlist.html`檔案是包含只顯示人員清單所需的 HTML 的部分檢視。</span><span class="sxs-lookup"><span data-stu-id="22c74-330">The `personlist.html` file is a partial view containing only the HTML needed to display person list.</span></span>

<span data-ttu-id="22c74-331">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/partials/personlist.html?highlight=3)]</span><span class="sxs-lookup"><span data-stu-id="22c74-331">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/partials/personlist.html?highlight=3)]</span></span>

<span data-ttu-id="22c74-332">控制器會定義使用的模組`controller`函式在*personListController.js*。</span><span class="sxs-lookup"><span data-stu-id="22c74-332">The controller is defined by using the module's `controller` function in *personListController.js*.</span></span>

<span data-ttu-id="22c74-333">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personListController.js?highlight=1)]</span><span class="sxs-lookup"><span data-stu-id="22c74-333">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/personListController.js?highlight=1)]</span></span>

<span data-ttu-id="22c74-334">如果我們執行此應用程式，並瀏覽至`people/spa#/persons`URL，我們會看到：</span><span class="sxs-lookup"><span data-stu-id="22c74-334">If we run this application and navigate to the `people/spa#/persons` URL, we will see:</span></span>

![人員清單檢視](angular/_static/spa-persons.png)

<span data-ttu-id="22c74-336">如果我們瀏覽至 [詳細資料] 頁面上，例如`people/spa#/persons/2`，我們會看到詳細資料的部分檢視：</span><span class="sxs-lookup"><span data-stu-id="22c74-336">If we navigate to a detail page, for example `people/spa#/persons/2`, we will see the detail partial view:</span></span>

![連絡人詳細資料檢視](angular/_static/spa-persons-2.png)

<span data-ttu-id="22c74-338">您可以檢視完整的來源並不會顯示在本文中的任何檔案[GitHub](https://github.com/aspnet/Docs/tree/master/aspnetcore/client-side/angular/sample)。</span><span class="sxs-lookup"><span data-stu-id="22c74-338">You can view the full source and any files not shown in this article on [GitHub](https://github.com/aspnet/Docs/tree/master/aspnetcore/client-side/angular/sample).</span></span>

### <a name="event-handlers"></a><span data-ttu-id="22c74-339">事件處理常式</span><span class="sxs-lookup"><span data-stu-id="22c74-339">Event Handlers</span></span>

<span data-ttu-id="22c74-340">數目中 HTML DOM 中的輸入項目加入事件處理功能的 AngularJS 指示詞</span><span class="sxs-lookup"><span data-stu-id="22c74-340">There are a number of directives in AngularJS that add event-handling capabilities to the input elements in your HTML DOM.</span></span> <span data-ttu-id="22c74-341">以下是內建 AngularJS 之事件的清單。</span><span class="sxs-lookup"><span data-stu-id="22c74-341">Below is a list of the events that are built into AngularJS.</span></span>

   * `ng-click`

   * `ng-dbl-click`

   * `ng-mousedown`

   * `ng-mouseup`

   * `ng-mouseenter`

   * `ng-mouseleave`

   * `ng-mousemove`

   * `ng-keydown`

   * `ng-keyup`

   * `ng-keypress`

   * `ng-change`

> [!NOTE]
> <span data-ttu-id="22c74-342">您可以加入自己的事件處理常式使用[AngularJS 中功能的自訂指示詞](https://docs.angularjs.org/guide/directive)。</span><span class="sxs-lookup"><span data-stu-id="22c74-342">You can add your own event handlers using the [custom directives feature in AngularJS](https://docs.angularjs.org/guide/directive).</span></span>

<span data-ttu-id="22c74-343">讓我們看看`ng-click`固定事件。</span><span class="sxs-lookup"><span data-stu-id="22c74-343">Let's look at how the `ng-click` event is wired up.</span></span> <span data-ttu-id="22c74-344">建立新的 JavaScript 檔名為*eventHandlerController.js*，並加入下列：</span><span class="sxs-lookup"><span data-stu-id="22c74-344">Create a new JavaScript file named *eventHandlerController.js*, and add the following to it:</span></span>

<span data-ttu-id="22c74-345">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/eventHandlerController.js?highlight=5,6,7)]</span><span class="sxs-lookup"><span data-stu-id="22c74-345">[!code-javascript[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/wwwroot/app/eventHandlerController.js?highlight=5,6,7)]</span></span>

<span data-ttu-id="22c74-346">請注意新`sayName`函式在`eventHandlerController`在線條上方 5。</span><span class="sxs-lookup"><span data-stu-id="22c74-346">Notice the new `sayName` function in `eventHandlerController` on line 5 above.</span></span> <span data-ttu-id="22c74-347">正在進行的所有方法的現在會顯示歡迎訊息與使用者 JavaScript 警示。</span><span class="sxs-lookup"><span data-stu-id="22c74-347">All the method is doing for now is showing a JavaScript alert to the user with a welcome message.</span></span>

<span data-ttu-id="22c74-348">下列檢視會將控制器函式繫結 AngularJS 事件。</span><span class="sxs-lookup"><span data-stu-id="22c74-348">The view below binds a controller function to an AngularJS event.</span></span> <span data-ttu-id="22c74-349">第 9 行上有一個按鈕`ng-click`角度指示詞已套用。</span><span class="sxs-lookup"><span data-stu-id="22c74-349">Line 9 has a button on which the `ng-click` Angular directive has been applied.</span></span> <span data-ttu-id="22c74-350">它會呼叫我們`sayName`函式，以附加至`$scope`傳遞到這個檢視的物件。</span><span class="sxs-lookup"><span data-stu-id="22c74-350">It calls our `sayName` function, which is attached to the `$scope` object passed to this view.</span></span>

<span data-ttu-id="22c74-351">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/People/Events.cshtml?highlight=9)]</span><span class="sxs-lookup"><span data-stu-id="22c74-351">[!code-html[Main](../client-side/angular/sample/AngularJSSample/src/AngularJSSample/Views/People/Events.cshtml?highlight=9)]</span></span>

<span data-ttu-id="22c74-352">執行中範例會示範控制站的`sayName`按鈕便會自動呼叫函式。</span><span class="sxs-lookup"><span data-stu-id="22c74-352">The running example demonstrates that the controller's `sayName` function is called automatically when the button is clicked.</span></span>

![Click 事件](angular/_static/events.png)

<span data-ttu-id="22c74-354">如需詳細 AngularJS 內建的事件處理常式指示詞的詳細資訊，請務必磁頭[文件網站](https://docs.angularjs.org/api/ng/directive/ngClick)的 AngularJS。</span><span class="sxs-lookup"><span data-stu-id="22c74-354">For more detail on AngularJS built-in event handler directives, be sure to head to the [documentation website](https://docs.angularjs.org/api/ng/directive/ngClick) of AngularJS.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="22c74-355">其他資源</span><span class="sxs-lookup"><span data-stu-id="22c74-355">Additional resources</span></span>

* [<span data-ttu-id="22c74-356">角度的文件</span><span class="sxs-lookup"><span data-stu-id="22c74-356">Angular Docs</span></span>](https://docs.angularjs.org)

* [<span data-ttu-id="22c74-357">角度 2 的資訊</span><span class="sxs-lookup"><span data-stu-id="22c74-357">Angular 2 Info</span></span>](https://angular.io/)