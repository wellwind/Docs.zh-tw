---
uid: web-api/overview/advanced/configuring-aspnet-web-api
title: "設定 ASP.NET Web API 2 |Microsoft 文件"
author: MikeWasson
description: 
ms.author: aspnetcontent
manager: wpickett
ms.date: 03/31/2014
ms.topic: article
ms.assetid: 9e10a700-8d91-4d2e-a31e-b8b569fe867c
ms.technology: dotnet-webapi
ms.prod: .net-framework
msc.legacyurl: /web-api/overview/advanced/configuring-aspnet-web-api
msc.type: authoredcontent
ms.openlocfilehash: f9b471fe2afdce278869a2e4d9b693a78030324b
ms.sourcegitcommit: 060879fcf3f73d2366b5c811986f8695fff65db8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2018
---
<a name="configuring-aspnet-web-api-2"></a><span data-ttu-id="85755-102">設定 ASP.NET Web API 2</span><span class="sxs-lookup"><span data-stu-id="85755-102">Configuring ASP.NET Web API 2</span></span>
====================
<span data-ttu-id="85755-103">由[Mike Wasson](https://github.com/MikeWasson)</span><span class="sxs-lookup"><span data-stu-id="85755-103">by [Mike Wasson](https://github.com/MikeWasson)</span></span>

<span data-ttu-id="85755-104">本主題描述如何設定 ASP.NET Web API。</span><span class="sxs-lookup"><span data-stu-id="85755-104">This topic describes how to configure ASP.NET Web API.</span></span>

- [<span data-ttu-id="85755-105">組態設定</span><span class="sxs-lookup"><span data-stu-id="85755-105">Configuration Settings</span></span>](#settings)
- [<span data-ttu-id="85755-106">設定與 ASP.NET 裝載的 Web 應用程式開發介面</span><span class="sxs-lookup"><span data-stu-id="85755-106">Configuring Web API with ASP.NET Hosting</span></span>](#webhost)
- [<span data-ttu-id="85755-107">設定與 OWIN 自我主控的 Web 應用程式開發介面</span><span class="sxs-lookup"><span data-stu-id="85755-107">Configuring Web API with OWIN Self-Hosting</span></span>](#selfhost)
- [<span data-ttu-id="85755-108">全域 Web API 服務</span><span class="sxs-lookup"><span data-stu-id="85755-108">Global Web API Services</span></span>](#services)
- [<span data-ttu-id="85755-109">每個控制站設定</span><span class="sxs-lookup"><span data-stu-id="85755-109">Per-Controller Configuration</span></span>](#percontrollerconfig)

<a id="settings"></a>
## <a name="configuration-settings"></a><span data-ttu-id="85755-110">組態設定</span><span class="sxs-lookup"><span data-stu-id="85755-110">Configuration Settings</span></span>

<span data-ttu-id="85755-111">中所定義的 web API 組態所[HttpConfiguration](https://msdn.microsoft.com/library/system.web.http.httpconfiguration.aspx)類別。</span><span class="sxs-lookup"><span data-stu-id="85755-111">Web API configuration setttings are defined in the [HttpConfiguration](https://msdn.microsoft.com/library/system.web.http.httpconfiguration.aspx) class.</span></span>

| <span data-ttu-id="85755-112">成員</span><span class="sxs-lookup"><span data-stu-id="85755-112">Member</span></span> | <span data-ttu-id="85755-113">描述</span><span class="sxs-lookup"><span data-stu-id="85755-113">Description</span></span> |
| --- | --- |
| <span data-ttu-id="85755-114">**DependencyResolver**</span><span class="sxs-lookup"><span data-stu-id="85755-114">**DependencyResolver**</span></span> | <span data-ttu-id="85755-115">可讓相依性插入控制站。</span><span class="sxs-lookup"><span data-stu-id="85755-115">Enables dependency injection for controllers.</span></span> <span data-ttu-id="85755-116">請參閱[使用 Web 應用程式開發介面的相依性解析程式](dependency-injection.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-116">See [Using the Web API Dependency Resolver](dependency-injection.md).</span></span> |
| <span data-ttu-id="85755-117">**篩選**</span><span class="sxs-lookup"><span data-stu-id="85755-117">**Filters**</span></span> | <span data-ttu-id="85755-118">動作篩選條件。</span><span class="sxs-lookup"><span data-stu-id="85755-118">Action filters.</span></span> |
| <span data-ttu-id="85755-119">**格式器**</span><span class="sxs-lookup"><span data-stu-id="85755-119">**Formatters**</span></span> | <span data-ttu-id="85755-120">[媒體類型格式器](../formats-and-model-binding/media-formatters.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-120">[Media-type formatters](../formats-and-model-binding/media-formatters.md).</span></span> |
| <span data-ttu-id="85755-121">**IncludeErrorDetailPolicy**</span><span class="sxs-lookup"><span data-stu-id="85755-121">**IncludeErrorDetailPolicy**</span></span> | <span data-ttu-id="85755-122">指定伺服器在 HTTP 回應訊息中是否包含錯誤詳細資料，例如例外狀況訊息和堆疊追蹤。</span><span class="sxs-lookup"><span data-stu-id="85755-122">Specifies whether the server should include error details, such as exception messages and stack traces, in HTTP response messages.</span></span> <span data-ttu-id="85755-123">請參閱[IncludeErrorDetailPolicy](https://msdn.microsoft.com/library/system.web.http.includeerrordetailpolicy(v=vs.108))。</span><span class="sxs-lookup"><span data-stu-id="85755-123">See [IncludeErrorDetailPolicy](https://msdn.microsoft.com/library/system.web.http.includeerrordetailpolicy(v=vs.108)).</span></span> |
| <span data-ttu-id="85755-124">**Initializer**</span><span class="sxs-lookup"><span data-stu-id="85755-124">**Initializer**</span></span> | <span data-ttu-id="85755-125">執行最後的初始化函式**HttpConfiguration**。</span><span class="sxs-lookup"><span data-stu-id="85755-125">A function that performs final initialization of the **HttpConfiguration**.</span></span> |
| <span data-ttu-id="85755-126">**MessageHandlers**</span><span class="sxs-lookup"><span data-stu-id="85755-126">**MessageHandlers**</span></span> | <span data-ttu-id="85755-127">[HTTP 訊息處理常式](http-message-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-127">[HTTP message handlers](http-message-handlers.md).</span></span> |
| <span data-ttu-id="85755-128">**ParameterBindingRules**</span><span class="sxs-lookup"><span data-stu-id="85755-128">**ParameterBindingRules**</span></span> | <span data-ttu-id="85755-129">用於控制器動作上的繫結參數的規則集合。</span><span class="sxs-lookup"><span data-stu-id="85755-129">A collection of rules for binding parameters on controller actions.</span></span> |
| <span data-ttu-id="85755-130">**屬性**</span><span class="sxs-lookup"><span data-stu-id="85755-130">**Properties**</span></span> | <span data-ttu-id="85755-131">一般屬性包。</span><span class="sxs-lookup"><span data-stu-id="85755-131">A generic property bag.</span></span> |
| <span data-ttu-id="85755-132">**路由**</span><span class="sxs-lookup"><span data-stu-id="85755-132">**Routes**</span></span> | <span data-ttu-id="85755-133">路由的集合。</span><span class="sxs-lookup"><span data-stu-id="85755-133">The collection of routes.</span></span> <span data-ttu-id="85755-134">請參閱[中 ASP.NET Web API 的路由](../web-api-routing-and-actions/routing-in-aspnet-web-api.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-134">See [Routing in ASP.NET Web API](../web-api-routing-and-actions/routing-in-aspnet-web-api.md).</span></span> |
| <span data-ttu-id="85755-135">**服務**</span><span class="sxs-lookup"><span data-stu-id="85755-135">**Services**</span></span> | <span data-ttu-id="85755-136">服務集合。</span><span class="sxs-lookup"><span data-stu-id="85755-136">The collection of services.</span></span> <span data-ttu-id="85755-137">請參閱[服務](#services)。</span><span class="sxs-lookup"><span data-stu-id="85755-137">See [Services](#services).</span></span> |


## <a name="prerequisites"></a><span data-ttu-id="85755-138">必要條件</span><span class="sxs-lookup"><span data-stu-id="85755-138">Prerequisites</span></span>

<span data-ttu-id="85755-139">[Visual Studio 2017](https://www.visualstudio.com/vs/) Community、 Professional 或 Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="85755-139">[Visual Studio 2017](https://www.visualstudio.com/vs/) Community, Professional, or Enterprise Edition.</span></span>

<a id="webhost"></a>
## <a name="configuring-web-api-with-aspnet-hosting"></a><span data-ttu-id="85755-140">設定與 ASP.NET 裝載的 Web 應用程式開發介面</span><span class="sxs-lookup"><span data-stu-id="85755-140">Configuring Web API with ASP.NET Hosting</span></span>

<span data-ttu-id="85755-141">ASP.NET 應用程式中，設定 Web 應用程式開發介面呼叫[GlobalConfiguration.Configure](https://msdn.microsoft.com/library/system.web.http.globalconfiguration.configure.aspx)中**應用程式\_啟動**方法。</span><span class="sxs-lookup"><span data-stu-id="85755-141">In an ASP.NET application, configure Web API by calling [GlobalConfiguration.Configure](https://msdn.microsoft.com/library/system.web.http.globalconfiguration.configure.aspx) in the **Application\_Start** method.</span></span> <span data-ttu-id="85755-142">**設定**方法會採用單一參數的型別與委派**HttpConfiguration**。</span><span class="sxs-lookup"><span data-stu-id="85755-142">The **Configure** method takes a delegate with a single parameter of type **HttpConfiguration**.</span></span> <span data-ttu-id="85755-143">執行所有的委派在您使用設定。</span><span class="sxs-lookup"><span data-stu-id="85755-143">Perform all of your configuation inside the delegate.</span></span>

<span data-ttu-id="85755-144">以下是使用在匿名委派的範例：</span><span class="sxs-lookup"><span data-stu-id="85755-144">Here is an example using an anonymous delegate:</span></span>

[!code-csharp[Main](configuring-aspnet-web-api/samples/sample1.cs)]

<span data-ttu-id="85755-145">在 Visual Studio 2017，「 ASP.NET Web 應用程式 」 專案範本會自動設定的組態程式碼中，如果您選取 「 Web 應用程式開發介面 」 中**新增 ASP.NET 專案**對話方塊。</span><span class="sxs-lookup"><span data-stu-id="85755-145">In Visual Studio 2017, the "ASP.NET Web Application" project template automatically sets up the configuration code, if you select "Web API" in the **New ASP.NET Project** dialog.</span></span>

[![](configuring-aspnet-web-api/_static/image2.png)](configuring-aspnet-web-api/_static/image1.png)

<span data-ttu-id="85755-146">專案範本建立名為在應用程式內 WebApiConfig.cs\_開始資料夾。</span><span class="sxs-lookup"><span data-stu-id="85755-146">The project template creates a file named WebApiConfig.cs inside the App\_Start folder.</span></span> <span data-ttu-id="85755-147">這個程式碼檔會定義應該放置 Web API 組態程式碼的委派。</span><span class="sxs-lookup"><span data-stu-id="85755-147">This code file defines the delegate where you should put your Web API configuration code.</span></span>

![](configuring-aspnet-web-api/_static/image3.png)

[!code-csharp[Main](configuring-aspnet-web-api/samples/sample2.cs?highlight=12)]

<span data-ttu-id="85755-148">專案範本也會加入程式碼呼叫的委派**應用程式\_啟動**。</span><span class="sxs-lookup"><span data-stu-id="85755-148">The project template also adds the code that calls the delegate from **Application\_Start**.</span></span>

[!code-csharp[Main](configuring-aspnet-web-api/samples/sample3.cs?highlight=5)]

<a id="selfhost"></a>
## <a name="configuring-web-api-with-owin-self-hosting"></a><span data-ttu-id="85755-149">設定與 OWIN 自我主控的 Web 應用程式開發介面</span><span class="sxs-lookup"><span data-stu-id="85755-149">Configuring Web API with OWIN Self-Hosting</span></span>

<span data-ttu-id="85755-150">如果您是自我裝載與 OWIN，建立新**HttpConfiguration**執行個體。</span><span class="sxs-lookup"><span data-stu-id="85755-150">If you are self-hosting with OWIN, create a new **HttpConfiguration** instance.</span></span> <span data-ttu-id="85755-151">這個執行個體上，執行任何設定，然後將傳遞至執行個體**Owin.UseWebApi**擴充方法。</span><span class="sxs-lookup"><span data-stu-id="85755-151">Perform any configuration on this instance, and then pass the instance to the **Owin.UseWebApi** extension method.</span></span>

[!code-csharp[Main](configuring-aspnet-web-api/samples/sample4.cs)]

<span data-ttu-id="85755-152">本教學課程[Self-Host ASP.NET Web API 2 使用 OWIN](../hosting-aspnet-web-api/use-owin-to-self-host-web-api.md)顯示完成的步驟。</span><span class="sxs-lookup"><span data-stu-id="85755-152">The tutorial [Use OWIN to Self-Host ASP.NET Web API 2](../hosting-aspnet-web-api/use-owin-to-self-host-web-api.md) shows the complete steps.</span></span>

<a id="services"></a>
## <a name="global-web-api-services"></a><span data-ttu-id="85755-153">全域 Web API 服務</span><span class="sxs-lookup"><span data-stu-id="85755-153">Global Web API Services</span></span>

<span data-ttu-id="85755-154">**HttpConfiguration.Services**集合包含一組通用 Web API 用來執行各種工作，例如控制器選取範圍和內容交涉的服務。</span><span class="sxs-lookup"><span data-stu-id="85755-154">The **HttpConfiguration.Services** collection contains a set of global services that Web API uses to perform various tasks, such as controller selection and content negotiation.</span></span>

> [!NOTE]
> <span data-ttu-id="85755-155">**服務**集合不是用於服務探索或相依性插入的一般用途機制。</span><span class="sxs-lookup"><span data-stu-id="85755-155">The **Services** collection is not a general-purpose mechanism for service discovery or dependency injection.</span></span> <span data-ttu-id="85755-156">它只會儲存至 Web API 架構已知的服務類型。</span><span class="sxs-lookup"><span data-stu-id="85755-156">It only stores service types that are known to the Web API framework.</span></span>


<span data-ttu-id="85755-157">**服務**集合已初始化與一組預設的服務，而且您可以提供您自己的自訂實作。</span><span class="sxs-lookup"><span data-stu-id="85755-157">The **Services** collection is initialized with a default set of services, and you can provide your own custom implementations.</span></span> <span data-ttu-id="85755-158">有些服務支援多個執行個體，而其他人可以有只有一個執行個體。</span><span class="sxs-lookup"><span data-stu-id="85755-158">Some services support multiple instances, while others can have only one instance.</span></span> <span data-ttu-id="85755-159">(不過，您也可以提供在控制器層級的服務，請參閱[每個控制站設定](#percontrollerconfig)。</span><span class="sxs-lookup"><span data-stu-id="85755-159">(However, you can also provide services at the controller level; see [Per-Controller Configuration](#percontrollerconfig).</span></span>

<span data-ttu-id="85755-160">單一執行個體的服務</span><span class="sxs-lookup"><span data-stu-id="85755-160">Single-Instance Services</span></span>


| <span data-ttu-id="85755-161">服務</span><span class="sxs-lookup"><span data-stu-id="85755-161">Service</span></span> | <span data-ttu-id="85755-162">描述</span><span class="sxs-lookup"><span data-stu-id="85755-162">Description</span></span> |
| --- | --- |
| <span data-ttu-id="85755-163">**IActionValueBinder**</span><span class="sxs-lookup"><span data-stu-id="85755-163">**IActionValueBinder**</span></span> | <span data-ttu-id="85755-164">取得參數繫結。</span><span class="sxs-lookup"><span data-stu-id="85755-164">Gets a binding for a parameter.</span></span> |
| <span data-ttu-id="85755-165">**IApiExplorer**</span><span class="sxs-lookup"><span data-stu-id="85755-165">**IApiExplorer**</span></span> | <span data-ttu-id="85755-166">取得描述元的應用程式所公開的 Api。</span><span class="sxs-lookup"><span data-stu-id="85755-166">Gets descriptions of the APIs exposed by the application.</span></span> <span data-ttu-id="85755-167">請參閱[建立 Web API 說明頁面](../getting-started-with-aspnet-web-api/creating-api-help-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-167">See [Creating a Help Page for a Web API](../getting-started-with-aspnet-web-api/creating-api-help-pages.md).</span></span> |
| <span data-ttu-id="85755-168">**IAssembliesResolver**</span><span class="sxs-lookup"><span data-stu-id="85755-168">**IAssembliesResolver**</span></span> | <span data-ttu-id="85755-169">取得應用程式的組件清單。</span><span class="sxs-lookup"><span data-stu-id="85755-169">Gets a list of the assemblies for the application.</span></span> <span data-ttu-id="85755-170">請參閱[路由和動作選取](../web-api-routing-and-actions/routing-and-action-selection.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-170">See [Routing and Action Selection](../web-api-routing-and-actions/routing-and-action-selection.md).</span></span> |
| <span data-ttu-id="85755-171">**IBodyModelValidator**</span><span class="sxs-lookup"><span data-stu-id="85755-171">**IBodyModelValidator**</span></span> | <span data-ttu-id="85755-172">驗證媒體類型格式器所讀取的要求主體的模型。</span><span class="sxs-lookup"><span data-stu-id="85755-172">Validates a model that is read from the request body by a media-type formatter.</span></span> |
| <span data-ttu-id="85755-173">**IContentNegotiator**</span><span class="sxs-lookup"><span data-stu-id="85755-173">**IContentNegotiator**</span></span> | <span data-ttu-id="85755-174">執行內容交涉。</span><span class="sxs-lookup"><span data-stu-id="85755-174">Performs content negotiation.</span></span> |
| <span data-ttu-id="85755-175">**IDocumentationProvider**</span><span class="sxs-lookup"><span data-stu-id="85755-175">**IDocumentationProvider**</span></span> | <span data-ttu-id="85755-176">提供 Api 文的件。</span><span class="sxs-lookup"><span data-stu-id="85755-176">Provides documentation for APIs.</span></span> <span data-ttu-id="85755-177">預設值是**null**。</span><span class="sxs-lookup"><span data-stu-id="85755-177">The default is **null**.</span></span> <span data-ttu-id="85755-178">請參閱[建立 Web API 說明頁面](../getting-started-with-aspnet-web-api/creating-api-help-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-178">See [Creating a Help Page for a Web API](../getting-started-with-aspnet-web-api/creating-api-help-pages.md).</span></span> |
| <span data-ttu-id="85755-179">**IHostBufferPolicySelector**</span><span class="sxs-lookup"><span data-stu-id="85755-179">**IHostBufferPolicySelector**</span></span> | <span data-ttu-id="85755-180">表示主機是否應緩衝 HTTP 訊息實體內文。</span><span class="sxs-lookup"><span data-stu-id="85755-180">Indicates whether the host should buffer HTTP message entity bodies.</span></span> |
| <span data-ttu-id="85755-181">**IHttpActionInvoker**</span><span class="sxs-lookup"><span data-stu-id="85755-181">**IHttpActionInvoker**</span></span> | <span data-ttu-id="85755-182">叫用控制器動作。</span><span class="sxs-lookup"><span data-stu-id="85755-182">Invokes a controller action.</span></span> <span data-ttu-id="85755-183">請參閱[路由和動作選取](../web-api-routing-and-actions/routing-and-action-selection.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-183">See [Routing and Action Selection](../web-api-routing-and-actions/routing-and-action-selection.md).</span></span> |
| <span data-ttu-id="85755-184">**IHttpActionSelector**</span><span class="sxs-lookup"><span data-stu-id="85755-184">**IHttpActionSelector**</span></span> | <span data-ttu-id="85755-185">選取控制器動作。</span><span class="sxs-lookup"><span data-stu-id="85755-185">Selects a controller action.</span></span> <span data-ttu-id="85755-186">請參閱[路由和動作選取](../web-api-routing-and-actions/routing-and-action-selection.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-186">See [Routing and Action Selection](../web-api-routing-and-actions/routing-and-action-selection.md).</span></span> |
| <span data-ttu-id="85755-187">**IHttpControllerActivator**</span><span class="sxs-lookup"><span data-stu-id="85755-187">**IHttpControllerActivator**</span></span> | <span data-ttu-id="85755-188">啟動控制站。</span><span class="sxs-lookup"><span data-stu-id="85755-188">Activates a controller.</span></span> <span data-ttu-id="85755-189">請參閱[路由和動作選取](../web-api-routing-and-actions/routing-and-action-selection.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-189">See [Routing and Action Selection](../web-api-routing-and-actions/routing-and-action-selection.md).</span></span> |
| <span data-ttu-id="85755-190">**IHttpControllerSelector**</span><span class="sxs-lookup"><span data-stu-id="85755-190">**IHttpControllerSelector**</span></span> | <span data-ttu-id="85755-191">選取控制器。</span><span class="sxs-lookup"><span data-stu-id="85755-191">Selects a controller.</span></span> <span data-ttu-id="85755-192">請參閱[路由和動作選取](../web-api-routing-and-actions/routing-and-action-selection.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-192">See [Routing and Action Selection](../web-api-routing-and-actions/routing-and-action-selection.md).</span></span> |
| <span data-ttu-id="85755-193">**IHttpControllerTypeResolver**</span><span class="sxs-lookup"><span data-stu-id="85755-193">**IHttpControllerTypeResolver**</span></span> | <span data-ttu-id="85755-194">提供一份應用程式中的 Web API 控制器類型。</span><span class="sxs-lookup"><span data-stu-id="85755-194">Provides a list of the Web API controller types in the application.</span></span> <span data-ttu-id="85755-195">請參閱[路由和動作選取](../web-api-routing-and-actions/routing-and-action-selection.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-195">See [Routing and Action Selection](../web-api-routing-and-actions/routing-and-action-selection.md).</span></span> |
| <span data-ttu-id="85755-196">**ITraceManager**</span><span class="sxs-lookup"><span data-stu-id="85755-196">**ITraceManager**</span></span> | <span data-ttu-id="85755-197">初始化追蹤架構。</span><span class="sxs-lookup"><span data-stu-id="85755-197">Initializes the tracing framework.</span></span> <span data-ttu-id="85755-198">請參閱[中 ASP.NET Web API 追蹤](../testing-and-debugging/tracing-in-aspnet-web-api.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-198">See [Tracing in ASP.NET Web API](../testing-and-debugging/tracing-in-aspnet-web-api.md).</span></span> |
| <span data-ttu-id="85755-199">**ITraceWriter**</span><span class="sxs-lookup"><span data-stu-id="85755-199">**ITraceWriter**</span></span> | <span data-ttu-id="85755-200">提供追蹤寫入器。</span><span class="sxs-lookup"><span data-stu-id="85755-200">Provides a trace writer.</span></span> <span data-ttu-id="85755-201">預設為 「 無操作 」 追蹤寫入器。</span><span class="sxs-lookup"><span data-stu-id="85755-201">The default is a "no-op" trace writer.</span></span> <span data-ttu-id="85755-202">請參閱[中 ASP.NET Web API 追蹤](../testing-and-debugging/tracing-in-aspnet-web-api.md)。</span><span class="sxs-lookup"><span data-stu-id="85755-202">See [Tracing in ASP.NET Web API](../testing-and-debugging/tracing-in-aspnet-web-api.md).</span></span> |
| <span data-ttu-id="85755-203">**IModelValidatorCache**</span><span class="sxs-lookup"><span data-stu-id="85755-203">**IModelValidatorCache**</span></span> | <span data-ttu-id="85755-204">提供模型驗證程式的快取。</span><span class="sxs-lookup"><span data-stu-id="85755-204">Provides a cache of model validators.</span></span> |

<span data-ttu-id="85755-205">多個執行個體的服務</span><span class="sxs-lookup"><span data-stu-id="85755-205">Multiple-Instance Services</span></span>


| <span data-ttu-id="85755-206">服務</span><span class="sxs-lookup"><span data-stu-id="85755-206">Service</span></span> | <span data-ttu-id="85755-207">描述</span><span class="sxs-lookup"><span data-stu-id="85755-207">Description</span></span> |
| --- | --- |
| <span data-ttu-id="85755-208">**IFilterProvider**</span><span class="sxs-lookup"><span data-stu-id="85755-208">**IFilterProvider**</span></span> | <span data-ttu-id="85755-209">傳回控制器動作的篩選清單。</span><span class="sxs-lookup"><span data-stu-id="85755-209">Returns a list of filters for a controller action.</span></span> |
| <span data-ttu-id="85755-210">**ModelBinderProvider**</span><span class="sxs-lookup"><span data-stu-id="85755-210">**ModelBinderProvider**</span></span> | <span data-ttu-id="85755-211">傳回指定型別的模型繫結。</span><span class="sxs-lookup"><span data-stu-id="85755-211">Returns a model binder for a given type.</span></span> |
| <span data-ttu-id="85755-212">**ModelMetadataProvider**</span><span class="sxs-lookup"><span data-stu-id="85755-212">**ModelMetadataProvider**</span></span> | <span data-ttu-id="85755-213">提供模型中繼資料。</span><span class="sxs-lookup"><span data-stu-id="85755-213">Provides metadata for a model.</span></span> |
| <span data-ttu-id="85755-214">**ModelValidatorProvider**</span><span class="sxs-lookup"><span data-stu-id="85755-214">**ModelValidatorProvider**</span></span> | <span data-ttu-id="85755-215">提供模型驗證程式。</span><span class="sxs-lookup"><span data-stu-id="85755-215">Provides a validator for a model.</span></span> |
| <span data-ttu-id="85755-216">**ValueProviderFactory**</span><span class="sxs-lookup"><span data-stu-id="85755-216">**ValueProviderFactory**</span></span> | <span data-ttu-id="85755-217">建立值提供者。</span><span class="sxs-lookup"><span data-stu-id="85755-217">Creates a value provider.</span></span> <span data-ttu-id="85755-218">如需詳細資訊，請參閱的 Mike 拖延部落格文章[如何在 WebAPI 中建立的自訂值提供者](https://blogs.msdn.com/b/jmstall/archive/2012/04/23/how-to-create-a-custom-value-provider-in-webapi.aspx)</span><span class="sxs-lookup"><span data-stu-id="85755-218">For more information, see Mike Stall's blog post [How to create a custom value provider in WebAPI](https://blogs.msdn.com/b/jmstall/archive/2012/04/23/how-to-create-a-custom-value-provider-in-webapi.aspx)</span></span> |<span data-ttu-id="85755-219">。</span><span class="sxs-lookup"><span data-stu-id="85755-219">.</span></span>

<span data-ttu-id="85755-220">若要加入多個執行個體服務的自訂實作，請呼叫**新增**或**插入**上**服務**集合：</span><span class="sxs-lookup"><span data-stu-id="85755-220">To add a custom implementation to a multi-instance service, call **Add** or **Insert** on the **Services** collection:</span></span>

[!code-csharp[Main](configuring-aspnet-web-api/samples/sample5.cs)]

<span data-ttu-id="85755-221">若要取代的自訂實作中的單一執行個體服務，請呼叫**取代**上**服務**集合：</span><span class="sxs-lookup"><span data-stu-id="85755-221">To replace a single-instance service with a custom implementation, call **Replace** on the **Services** collection:</span></span>

[!code-csharp[Main](configuring-aspnet-web-api/samples/sample6.cs)]

<a id="percontrollerconfig"></a>
## <a name="per-controller-configuration"></a><span data-ttu-id="85755-222">每個控制站設定</span><span class="sxs-lookup"><span data-stu-id="85755-222">Per-Controller Configuration</span></span>

<span data-ttu-id="85755-223">您可以覆寫每個控制站為基礎的下列設定：</span><span class="sxs-lookup"><span data-stu-id="85755-223">You can override the following settings on a per-controller basis:</span></span>

- <span data-ttu-id="85755-224">媒體類型格式器</span><span class="sxs-lookup"><span data-stu-id="85755-224">Media-type formatters</span></span>
- <span data-ttu-id="85755-225">參數繫結規則</span><span class="sxs-lookup"><span data-stu-id="85755-225">Parameter binding rules</span></span>
- <span data-ttu-id="85755-226">服務</span><span class="sxs-lookup"><span data-stu-id="85755-226">Services</span></span>

<span data-ttu-id="85755-227">若要這樣做，請定義自訂屬性來實作**IControllerConfiguration**介面。</span><span class="sxs-lookup"><span data-stu-id="85755-227">To do so, define a custom attribute that implements the **IControllerConfiguration** interface.</span></span> <span data-ttu-id="85755-228">然後將屬性套用至控制器。</span><span class="sxs-lookup"><span data-stu-id="85755-228">Then apply the attribute to the controller.</span></span>

<span data-ttu-id="85755-229">下列範例以自訂格式子取代預設媒體類型格式器。</span><span class="sxs-lookup"><span data-stu-id="85755-229">The following example replaces the default media-type formatters with a custom formatter.</span></span>

[!code-csharp[Main](configuring-aspnet-web-api/samples/sample7.cs)]

<span data-ttu-id="85755-230">**IControllerConfiguration.Initialize**方法會採用兩個參數：</span><span class="sxs-lookup"><span data-stu-id="85755-230">The **IControllerConfiguration.Initialize** method takes two parameters:</span></span>

- <span data-ttu-id="85755-231">**HttpControllerSettings**物件</span><span class="sxs-lookup"><span data-stu-id="85755-231">An **HttpControllerSettings** object</span></span>
- <span data-ttu-id="85755-232">**HttpControllerDescriptor**物件</span><span class="sxs-lookup"><span data-stu-id="85755-232">An **HttpControllerDescriptor** object</span></span>

<span data-ttu-id="85755-233">**HttpControllerDescriptor**包含控制站，您可以檢查僅供參考之用 （例如，若要在區別兩個控制站） 的描述。</span><span class="sxs-lookup"><span data-stu-id="85755-233">The **HttpControllerDescriptor** contains a description of the controller, which you can examine for informational purposes (say, to distinguish between two controllers).</span></span>

<span data-ttu-id="85755-234">使用**HttpControllerSettings**物件來設定控制器。</span><span class="sxs-lookup"><span data-stu-id="85755-234">Use the **HttpControllerSettings** object to configure the controller.</span></span> <span data-ttu-id="85755-235">此物件包含您可以覆寫每個控制站為基礎的組態參數的子集。</span><span class="sxs-lookup"><span data-stu-id="85755-235">This object contains the subset of configuration parameters that you can override on a per-controller basis.</span></span> <span data-ttu-id="85755-236">請不要變更任何設定預設為全域**HttpConfiguration**物件。</span><span class="sxs-lookup"><span data-stu-id="85755-236">Any settings that you don't change default to the global **HttpConfiguration** object.</span></span>