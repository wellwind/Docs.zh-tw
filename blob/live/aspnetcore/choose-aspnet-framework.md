---
title: "在 ASP.NET 和 ASP.NET Core 之間進行選擇"
author: rick-anderson
description: "了解如何在 ASP.NET 和 ASP.NET Core 之間進行選擇。"
ms.author: riande
manager: wpickett
ms.date: 09/30/2017
ms.topic: article
ms.technology: aspnet
ms.prod: asp.net-core
uid: fundamentals/choose-between-aspnet-and-aspnetcore
ms.openlocfilehash: c909c9a852549577c4a9fbc461aaf3f710b301ef
ms.sourcegitcommit: 3e303620a125325bb9abd4b2d315c106fb8c47fd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2018
---
# <a name="choose-between-aspnet-and-aspnet-core"></a><span data-ttu-id="49f4a-103">在 ASP.NET 和 ASP.NET Core 之間進行選擇</span><span class="sxs-lookup"><span data-stu-id="49f4a-103">Choose between ASP.NET and ASP.NET Core</span></span> 

<span data-ttu-id="49f4a-104">不論您要建立哪種 Web 應用程式，ASP.NET 都為您提供了解決方案：從以 Windows Server 為目標的企業 Web 應用程式，到以 Linux 容器為目標的小型微服務，以及這兩者之間的所有項目。</span><span class="sxs-lookup"><span data-stu-id="49f4a-104">No matter the web application you are creating, ASP.NET has a solution for you: from enterprise web applications targeting Windows Server, to small microservices targeting Linux containers, and everything in between.</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="49f4a-105">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="49f4a-105">ASP.NET Core</span></span>

<span data-ttu-id="49f4a-106">ASP.NET Core 是一種開放原始碼、跨平台的架構，用於在 Windows、macOS 或 Linux 上建置現代化的雲端式 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="49f4a-106">ASP.NET Core is an open-source, cross-platform framework for building modern, cloud-based web applications on Windows, macOS, or Linux.</span></span>

## <a name="aspnet"></a><span data-ttu-id="49f4a-107">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="49f4a-107">ASP.NET</span></span>

<span data-ttu-id="49f4a-108">ASP.NET 是一種成熟的架構，提供了建置企業級伺服器端 Web 應用程式所需的所有服務。</span><span class="sxs-lookup"><span data-stu-id="49f4a-108">ASP.NET is a mature framework that provides all the services needed to build enterprise-class, server-based web applications on Windows.</span></span>

## <a name="which-one-is-right-for-me"></a><span data-ttu-id="49f4a-109">哪一個最適合我？</span><span class="sxs-lookup"><span data-stu-id="49f4a-109">Which one is right for me?</span></span>

| <span data-ttu-id="49f4a-110">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="49f4a-110">ASP.NET Core</span></span> | <span data-ttu-id="49f4a-111">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="49f4a-111">ASP.NET</span></span> |
|---|---|
|<span data-ttu-id="49f4a-112">為 Windows、macOS 或 Linux 建置</span><span class="sxs-lookup"><span data-stu-id="49f4a-112">Build for Windows, macOS, or Linux</span></span>|<span data-ttu-id="49f4a-113">為 Windows 建置</span><span class="sxs-lookup"><span data-stu-id="49f4a-113">Build for Windows</span></span>|
|<span data-ttu-id="49f4a-114">[Razor 頁面](xref:mvc/razor-pages/index)是使用 ASP.NET Core 2.0 建立 Web UI 的建議方法。</span><span class="sxs-lookup"><span data-stu-id="49f4a-114">[Razor Pages](xref:mvc/razor-pages/index) is the recommended approach to create a Web UI with ASP.NET Core 2.0.</span></span> <span data-ttu-id="49f4a-115">另請參閱 [MVC](xref:mvc/overview) 和 [Web API](xref:tutorials/first-web-api)</span><span class="sxs-lookup"><span data-stu-id="49f4a-115">See also [MVC](xref:mvc/overview) and [Web API](xref:tutorials/first-web-api)</span></span>|<span data-ttu-id="49f4a-116">使用 [Web Forms](https://docs.microsoft.com/aspnet/web-forms)、[SignalR](https://docs.microsoft.com/aspnet/signalr)、[MVC](https://docs.microsoft.com/aspnet/mvc)、[Web API](https://docs.microsoft.com/aspnet/web-api/) 或 [Web Pages](https://docs.microsoft.com/aspnet/web-pages)</span><span class="sxs-lookup"><span data-stu-id="49f4a-116">Use [Web Forms](https://docs.microsoft.com/aspnet/web-forms), [SignalR](https://docs.microsoft.com/aspnet/signalr), [MVC](https://docs.microsoft.com/aspnet/mvc), [Web API](https://docs.microsoft.com/aspnet/web-api/), or [Web Pages](https://docs.microsoft.com/aspnet/web-pages)</span></span>|
|<span data-ttu-id="49f4a-117">每部電腦多個版本</span><span class="sxs-lookup"><span data-stu-id="49f4a-117">Multiple versions per machine</span></span>|<span data-ttu-id="49f4a-118">每部電腦一個版本</span><span class="sxs-lookup"><span data-stu-id="49f4a-118">One version per machine</span></span>|
|<span data-ttu-id="49f4a-119">在 Visual Studio、[Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/) 或 [Visual Studio Code](https://code.visualstudio.com/) 中使用 C# 或 F# 進行開發</span><span class="sxs-lookup"><span data-stu-id="49f4a-119">Develop with Visual Studio, [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/), or [Visual Studio Code](https://code.visualstudio.com/) using C# or F#</span></span>|<span data-ttu-id="49f4a-120">在 Visual Studio 中使用 C#、VB 或 F# 進行開發</span><span class="sxs-lookup"><span data-stu-id="49f4a-120">Develop with Visual Studio using C#, VB, or F#</span></span>|
|<span data-ttu-id="49f4a-121">效能比 ASP.NET 更高</span><span class="sxs-lookup"><span data-stu-id="49f4a-121">Higher performance than ASP.NET</span></span>|<span data-ttu-id="49f4a-122">效能良好</span><span class="sxs-lookup"><span data-stu-id="49f4a-122">Good performance</span></span>|
|[<span data-ttu-id="49f4a-123">選擇 .NET Framework 或.NET Core 執行階段</span><span class="sxs-lookup"><span data-stu-id="49f4a-123">Choose .NET Framework or .NET Core runtime</span></span>](https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server)|<span data-ttu-id="49f4a-124">使用 .NET Framework 執行階段</span><span class="sxs-lookup"><span data-stu-id="49f4a-124">Use .NET Framework runtime</span></span>|

## <a name="aspnet-core-scenarios"></a><span data-ttu-id="49f4a-125">ASP.NET Core 案例</span><span class="sxs-lookup"><span data-stu-id="49f4a-125">ASP.NET Core scenarios</span></span>

<!-- update link to Razor Pages mvc movie series when done -->
* <span data-ttu-id="49f4a-126">[Razor 頁面](xref:mvc/razor-pages/index)是使用 ASP.NET Core 2.0 建立 Web UI 的建議方法。</span><span class="sxs-lookup"><span data-stu-id="49f4a-126">[Razor Pages](xref:mvc/razor-pages/index) is the recommended approach to create a Web UI with ASP.NET Core 2.0.</span></span>
* [<span data-ttu-id="49f4a-127">網站</span><span class="sxs-lookup"><span data-stu-id="49f4a-127">Websites</span></span>](xref:tutorials/first-mvc-app/index)
* [<span data-ttu-id="49f4a-128">API</span><span class="sxs-lookup"><span data-stu-id="49f4a-128">APIs</span></span>](xref:tutorials/first-web-api)

## <a name="aspnet-scenarios"></a><span data-ttu-id="49f4a-129">ASP.NET 案例</span><span class="sxs-lookup"><span data-stu-id="49f4a-129">ASP.NET scenarios</span></span>

* [<span data-ttu-id="49f4a-130">網站</span><span class="sxs-lookup"><span data-stu-id="49f4a-130">Websites</span></span>](https://docs.microsoft.com/aspnet/mvc)
* [<span data-ttu-id="49f4a-131">API</span><span class="sxs-lookup"><span data-stu-id="49f4a-131">APIs</span></span>](https://docs.microsoft.com/aspnet/web-api)
* [<span data-ttu-id="49f4a-132">即時</span><span class="sxs-lookup"><span data-stu-id="49f4a-132">Real-time</span></span>](https://docs.microsoft.com/aspnet/signalr)

## <a name="resources"></a><span data-ttu-id="49f4a-133">資源</span><span class="sxs-lookup"><span data-stu-id="49f4a-133">Resources</span></span>

* [<span data-ttu-id="49f4a-134">ASP.NET 簡介</span><span class="sxs-lookup"><span data-stu-id="49f4a-134">Introduction to ASP.NET</span></span>](https://docs.microsoft.com/aspnet/overview)
* [<span data-ttu-id="49f4a-135">ASP.NET Core 簡介</span><span class="sxs-lookup"><span data-stu-id="49f4a-135">Introduction to ASP.NET Core</span></span>](xref:index)