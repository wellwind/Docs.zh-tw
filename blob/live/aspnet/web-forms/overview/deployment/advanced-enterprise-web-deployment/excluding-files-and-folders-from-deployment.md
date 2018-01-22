---
uid: web-forms/overview/deployment/advanced-enterprise-web-deployment/excluding-files-and-folders-from-deployment
title: "檔案和資料夾排除部署 |Microsoft 文件"
author: jrjlee
description: "本主題描述如何您可以排除檔案和資料夾從 web 部署套件時建置及封裝的 web 應用程式專案。"
ms.author: aspnetcontent
manager: wpickett
ms.date: 05/04/2012
ms.topic: article
ms.assetid: f4cc2d40-6a78-429b-b06f-07d000d4caad
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/deployment/advanced-enterprise-web-deployment/excluding-files-and-folders-from-deployment
msc.type: authoredcontent
ms.openlocfilehash: 80810415bac473a58f60110fb9d08772e0627bd5
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2017
---
<a name="excluding-files-and-folders-from-deployment"></a><span data-ttu-id="c6767-103">從部署中排除檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="c6767-103">Excluding Files and Folders from Deployment</span></span>
====================
<span data-ttu-id="c6767-104">由[Jason Lee](https://github.com/jrjlee)</span><span class="sxs-lookup"><span data-stu-id="c6767-104">by [Jason Lee](https://github.com/jrjlee)</span></span>

[<span data-ttu-id="c6767-105">下載 PDF</span><span class="sxs-lookup"><span data-stu-id="c6767-105">Download PDF</span></span>](https://msdnshared.blob.core.windows.net/media/MSDNBlogsFS/prod.evol.blogs.msdn.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/63/56/8130.DeployingWebAppsInEnterpriseScenarios.pdf)

> <span data-ttu-id="c6767-106">本主題描述如何您可以排除檔案和資料夾從 web 部署套件時建置及封裝的 web 應用程式專案。</span><span class="sxs-lookup"><span data-stu-id="c6767-106">This topic describes how you can exclude files and folders from a web deployment package when you build and package a web application project.</span></span>


<span data-ttu-id="c6767-107">本主題根據名為 Fabrikam，Inc.的虛構公司的企業部署需求的教學課程系列的一部分此教學課程使用範例方案 & #x 2014;[連絡人管理員解決方案](../web-deployment-in-the-enterprise/the-contact-manager-solution.md)（& s) 來代表實際的層級的複雜性，包括 ASP.NET MVC 3 應用程式時，Windows 與 web 應用程式的 #x 2014;Communication Foundation (WCF) 服務，與資料庫專案。</span><span class="sxs-lookup"><span data-stu-id="c6767-107">This topic forms part of a series of tutorials based around the enterprise deployment requirements of a fictional company named Fabrikam, Inc. This tutorial series uses a sample solution&#x2014;the [Contact Manager solution](../web-deployment-in-the-enterprise/the-contact-manager-solution.md)&#x2014;to represent a web application with a realistic level of complexity, including an ASP.NET MVC 3 application, a Windows Communication Foundation (WCF) service, and a database project.</span></span>

<span data-ttu-id="c6767-108">這些教學課程的核心的部署方法為基礎所說明的分割專案檔案方法[了解專案檔](../web-deployment-in-the-enterprise/understanding-the-project-file.md)，這在建置程序由兩個專案中檔案 & #x 2014; 一個包含建置適用於每個目的地環境中和包含特定環境的建置和部署設定的指示。</span><span class="sxs-lookup"><span data-stu-id="c6767-108">The deployment method at the heart of these tutorials is based on the split project file approach described in [Understanding the Project File](../web-deployment-in-the-enterprise/understanding-the-project-file.md), in which the build process is controlled by two project files&#x2014;one containing build instructions that apply to every destination environment, and one containing environment-specific build and deployment settings.</span></span> <span data-ttu-id="c6767-109">在建置時，環境特定專案檔就會合併環境無從驗證專案檔來形成一組完整組建指示。</span><span class="sxs-lookup"><span data-stu-id="c6767-109">At build time, the environment-specific project file is merged into the environment-agnostic project file to form a complete set of build instructions.</span></span>

## <a name="overview"></a><span data-ttu-id="c6767-110">概觀</span><span class="sxs-lookup"><span data-stu-id="c6767-110">Overview</span></span>

<span data-ttu-id="c6767-111">當您建置 Visual Studio 2010 中的 web 應用程式專案時，Web 發行管線 (WPP) 可讓您擴充這個建置流程所編譯的 web 應用程式分成可部署 web 封裝的封裝。</span><span class="sxs-lookup"><span data-stu-id="c6767-111">When you build a web application project in Visual Studio 2010, the Web Publishing Pipeline (WPP) lets you extend this build process by packaging your compiled web application into a deployable web package.</span></span> <span data-ttu-id="c6767-112">然後，您可以用於網際網路資訊服務 (IIS) Web Deployment Tool (Web Deploy) 將此 web 封裝部署到遠端的 IIS 網頁伺服器，或匯入 web 套件手動透過 IIS 管理員。</span><span class="sxs-lookup"><span data-stu-id="c6767-112">You can then use the Internet Information Services (IIS) Web Deployment Tool (Web Deploy) to deploy this web package to a remote IIS web server, or import the web package manually through IIS Manager.</span></span> <span data-ttu-id="c6767-113">此封裝程序中會說明[建置和封裝 Web 應用程式專案](../web-deployment-in-the-enterprise/building-and-packaging-web-application-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="c6767-113">This packaging process is explained in [Building and Packaging Web Application Projects](../web-deployment-in-the-enterprise/building-and-packaging-web-application-projects.md).</span></span>

<span data-ttu-id="c6767-114">您如何在控制取得包含在您的 web 內容套件嗎？</span><span class="sxs-lookup"><span data-stu-id="c6767-114">So how do you control what gets included in your web package?</span></span> <span data-ttu-id="c6767-115">在 Visual Studio 中的專案設定，透過基礎的專案檔中，有很多的案例提供足夠的控制。</span><span class="sxs-lookup"><span data-stu-id="c6767-115">The project settings in Visual Studio, through the underlying project file, provide sufficient control for a lot of scenarios.</span></span> <span data-ttu-id="c6767-116">不過，在某些情況下您可能要調整您的 web 封裝到特定目的地環境的內容。</span><span class="sxs-lookup"><span data-stu-id="c6767-116">However, in some cases you may want to tailor the contents of your web package to specific destination environments.</span></span> <span data-ttu-id="c6767-117">比方說，您可能想要包含記錄檔的資料夾，當應用程式部署至測試環境，但當您部署至預備或生產環境應用程式中排除的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c6767-117">For example, you might want to include a folder for log files when you deploy your application to a test environment but exclude the folder when you deploy the application to a staging or production environment.</span></span> <span data-ttu-id="c6767-118">本主題將說明如何執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="c6767-118">This topic will show you how to do this.</span></span>

## <a name="what-gets-included-by-default"></a><span data-ttu-id="c6767-119">根據預設，取得包含內容？</span><span class="sxs-lookup"><span data-stu-id="c6767-119">What Gets Included by Default?</span></span>

<span data-ttu-id="c6767-120">當您在 Visual Studio 中，設定 web 應用程式專案屬性中**要部署的項目**清單**封裝/發行 Web**頁面可讓您指定您想要包含在您的 web 部署封裝。</span><span class="sxs-lookup"><span data-stu-id="c6767-120">When you configure your web application project properties in Visual Studio, the **Items to deploy** list on the **Package/Publish Web** page lets you specify what you want to include in your web deployment package.</span></span> <span data-ttu-id="c6767-121">根據預設，這設定為**僅執行此應用程式所需的檔案**。</span><span class="sxs-lookup"><span data-stu-id="c6767-121">By default, this is set to **Only files needed to run this application**.</span></span>

![](excluding-files-and-folders-from-deployment/_static/image1.png)

<span data-ttu-id="c6767-122">當您選擇**僅執行此應用程式所需的檔案**，WPP 會嘗試判斷哪些檔案應該加入至 web 套件。</span><span class="sxs-lookup"><span data-stu-id="c6767-122">When you choose **Only files needed to run this application**, the WPP will try to determine which files should be added to the web package.</span></span> <span data-ttu-id="c6767-123">包括：</span><span class="sxs-lookup"><span data-stu-id="c6767-123">This includes:</span></span>

- <span data-ttu-id="c6767-124">所有組建都輸出的專案。</span><span class="sxs-lookup"><span data-stu-id="c6767-124">All the build outputs for the project.</span></span>
- <span data-ttu-id="c6767-125">任何檔案的建置動作以標示**內容**。</span><span class="sxs-lookup"><span data-stu-id="c6767-125">Any files marked with a build action of **Content**.</span></span>

> [!NOTE]
> <span data-ttu-id="c6767-126">決定要包含哪些檔案的邏輯包含在這個檔案：</span><span class="sxs-lookup"><span data-stu-id="c6767-126">The logic that determines which files to include is contained in this file:</span></span>   
> <span data-ttu-id="c6767-127">*%PROGRAMFILES%\MSBuild\Microsoft\VisualStudio\v10.0\Web\ Microsoft.Web.Publishing.OnlyFilesToRunTheApp.targets*</span><span class="sxs-lookup"><span data-stu-id="c6767-127">*%PROGRAMFILES%\MSBuild\Microsoft\VisualStudio\v10.0\Web\ Microsoft.Web.Publishing.OnlyFilesToRunTheApp.targets*</span></span>


## <a name="excluding-specific-files-and-folders"></a><span data-ttu-id="c6767-128">排除特定檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="c6767-128">Excluding Specific Files and Folders</span></span>

<span data-ttu-id="c6767-129">在某些情況下，您會想更細部的掌控哪些檔案和資料夾部署。</span><span class="sxs-lookup"><span data-stu-id="c6767-129">In some cases, you'll want more fine-grained control over which files and folders are deployed.</span></span> <span data-ttu-id="c6767-130">如果您知道您想要排除之前有哪些的檔案的時間，而且排除套用到所有目的地環境，您可以直接將**建置動作**的每個檔案**無**。</span><span class="sxs-lookup"><span data-stu-id="c6767-130">If you know which files you want to exclude ahead of time, and the exclusion applies to all destination environments, you can simply set the **Build Action** of each file to **None**.</span></span>

<span data-ttu-id="c6767-131">**若要從部署中排除特定的檔案**</span><span class="sxs-lookup"><span data-stu-id="c6767-131">**To exclude specific files from deployment**</span></span>

1. <span data-ttu-id="c6767-132">在**方案總管 中**視窗中，以滑鼠右鍵按一下檔案，然後**屬性**。</span><span class="sxs-lookup"><span data-stu-id="c6767-132">In the **Solution Explorer** window, right-click the file, and then click **Properties**.</span></span>
2. <span data-ttu-id="c6767-133">在**屬性**視窗，請在**建置動作**列中選取**無**。</span><span class="sxs-lookup"><span data-stu-id="c6767-133">In the **Properties** window, in the **Build Action** row, select **None**.</span></span>

<span data-ttu-id="c6767-134">不過，這個方法不一定很方便。</span><span class="sxs-lookup"><span data-stu-id="c6767-134">However, this approach is not always convenient.</span></span> <span data-ttu-id="c6767-135">例如，您可能想要更改的檔案和資料夾都包含根據目的地環境中，以及從 Visual Studio 外部。</span><span class="sxs-lookup"><span data-stu-id="c6767-135">For example, you may want to vary which files and folders are included according to your destination environment, and from outside Visual Studio.</span></span> <span data-ttu-id="c6767-136">例如，在連絡人管理員範例方案中，看看 ContactManager.Mvc 專案的內容：</span><span class="sxs-lookup"><span data-stu-id="c6767-136">For example, in the Contact Manager sample solution, take a look at the contents of the ContactManager.Mvc project:</span></span>

![](excluding-files-and-folders-from-deployment/_static/image2.png)

- <span data-ttu-id="c6767-137">[內部] 資料夾包含一些 SQL 指令碼開發人員用來建立、 卸除，並填入本機資料庫，供開發應用程式。</span><span class="sxs-lookup"><span data-stu-id="c6767-137">The Internal folder contains some SQL scripts that the developer uses to create, drop, and populate local databases for development purposes.</span></span> <span data-ttu-id="c6767-138">在此資料夾中為 nothing 應該部署到預備或生產環境。</span><span class="sxs-lookup"><span data-stu-id="c6767-138">Nothing in this folder should be deployed to a staging or production environment.</span></span>
- <span data-ttu-id="c6767-139">指令碼 資料夾包含數個 JavaScript 檔案。</span><span class="sxs-lookup"><span data-stu-id="c6767-139">The Scripts folder contains several JavaScript files.</span></span> <span data-ttu-id="c6767-140">許多這些檔案會包含只是為了支援偵錯，或提供 Visual Studio 中的 IntelliSense。</span><span class="sxs-lookup"><span data-stu-id="c6767-140">A lot of these files are included purely to support debugging or provide IntelliSense in Visual Studio.</span></span> <span data-ttu-id="c6767-141">這當中有些檔案應該不會部署到預備環境或生產環境中。</span><span class="sxs-lookup"><span data-stu-id="c6767-141">Some of these files should not be deployed to staging or production environments.</span></span> <span data-ttu-id="c6767-142">不過，您可能想要將其部署至開發人員的測試環境，以利於進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="c6767-142">However, you may want to deploy them to a developer test environment to facilitate troubleshooting.</span></span>

<span data-ttu-id="c6767-143">雖然您無法管理您的專案檔案，以排除特定檔案和資料夾，還有更簡單的方法。</span><span class="sxs-lookup"><span data-stu-id="c6767-143">Although you could manipulate your project files to exclude specific files and folders, there is an easier way.</span></span> <span data-ttu-id="c6767-144">WPP 還有一個機制，藉由建置名為的項目清單中排除檔案和資料夾**ExcludeFromPackageFolders**和**ExcludeFromPackageFiles**。</span><span class="sxs-lookup"><span data-stu-id="c6767-144">The WPP includes a mechanism to exclude files and folders by building item lists named **ExcludeFromPackageFolders** and **ExcludeFromPackageFiles**.</span></span> <span data-ttu-id="c6767-145">您可以擴充這個機制，將您自己的項目加入至這些清單。</span><span class="sxs-lookup"><span data-stu-id="c6767-145">You can extend this mechanism by adding your own items to these lists.</span></span> <span data-ttu-id="c6767-146">若要這樣做，您需要完成下列高階步驟：</span><span class="sxs-lookup"><span data-stu-id="c6767-146">To do this, you need to complete these high-level steps:</span></span>

1. <span data-ttu-id="c6767-147">建立自訂專案檔名為*[專案名稱].wpp.targets*專案檔相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="c6767-147">Create a custom project file named *[project name].wpp.targets* in the same folder as your project file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c6767-148">*。 Wpp.targets*檔案必須放在與您的 web 應用程式專案檔 & #x 2014; 相同的資料夾，例如*ContactManager.Mvc.csproj*（& d) 做為任何 #x 2014; 而在同一個資料夾您用來控制組建和部署程序的自訂專案檔案。</span><span class="sxs-lookup"><span data-stu-id="c6767-148">The *.wpp.targets* file needs to go in the same folder as your web application project file&#x2014;for example, *ContactManager.Mvc.csproj*&#x2014;rather than in the same folder as any custom project files you use to control the build and deployment process.</span></span>
2. <span data-ttu-id="c6767-149">在*。 wpp.targets* file、 add **ItemGroup**項目。</span><span class="sxs-lookup"><span data-stu-id="c6767-149">In the *.wpp.targets* file, add an **ItemGroup** element.</span></span>
3. <span data-ttu-id="c6767-150">在**ItemGroup**項目，加入**ExcludeFromPackageFolders**和**ExcludeFromPackageFiles**来排除特定檔案和資料夾做為必要項目。</span><span class="sxs-lookup"><span data-stu-id="c6767-150">In the **ItemGroup** element, add **ExcludeFromPackageFolders** and **ExcludeFromPackageFiles** items to exclude specific files and folders as required.</span></span>

<span data-ttu-id="c6767-151">這是這個基本結構*。 wpp.targets*檔案：</span><span class="sxs-lookup"><span data-stu-id="c6767-151">This is the basic structure of this *.wpp.targets* file:</span></span>


[!code-xml[Main](excluding-files-and-folders-from-deployment/samples/sample1.xml)]


<span data-ttu-id="c6767-152">請注意每個項目包含名為的項目中繼資料元素**FromTarget**。</span><span class="sxs-lookup"><span data-stu-id="c6767-152">Note that each item includes an item metadata element named **FromTarget**.</span></span> <span data-ttu-id="c6767-153">這是選擇性的值並不會影響在建置程序。它只是用來指出特定檔案或資料夾已省略為什麼如果有人檢閱組建記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c6767-153">This is an optional value that doesn't affect the build process; it simply serves to indicate why particular files or folders were omitted if someone reviews the build logs.</span></span>

## <a name="excluding-files-and-folders-from-a-web-package"></a><span data-ttu-id="c6767-154">從 Web 套件中排除檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="c6767-154">Excluding Files and Folders from a Web Package</span></span>

<span data-ttu-id="c6767-155">下一個程序會示範如何加入*。 wpp.targets* web 應用程式專案，以及如何使用檔案時，排除特定檔案和資料夾從 web 套件建置您的專案檔案。</span><span class="sxs-lookup"><span data-stu-id="c6767-155">The next procedure shows you how to add a *.wpp.targets* file to a web application project and how to use the file to exclude specific files and folders from the web package when you build your project.</span></span>

<span data-ttu-id="c6767-156">**若要從 web 部署套件中排除檔案和資料夾**</span><span class="sxs-lookup"><span data-stu-id="c6767-156">**To exclude files and folders from a web deployment package**</span></span>

1. <span data-ttu-id="c6767-157">Visual Studio 2010 中開啟您的方案。</span><span class="sxs-lookup"><span data-stu-id="c6767-157">Open your solution in Visual Studio 2010.</span></span>
2. <span data-ttu-id="c6767-158">在**方案總管] 中**視窗中，以滑鼠右鍵按一下您 web 應用程式的專案節點 (比方說， **ContactManager.Mvc**)，指向**新增**，然後按一下 [ **新項目**。</span><span class="sxs-lookup"><span data-stu-id="c6767-158">In the **Solution Explorer** window, right-click your web application project node (for example, **ContactManager.Mvc**), point to **Add**, and then click **New Item**.</span></span>
3. <span data-ttu-id="c6767-159">在**加入新項目**對話方塊中，選取**XML 檔案**範本。</span><span class="sxs-lookup"><span data-stu-id="c6767-159">In the **Add New Item** dialog box, select the **XML File** template.</span></span>
4. <span data-ttu-id="c6767-160">在**名稱**方塊中，輸入*[專案名稱]***。 wpp.targets** (例如， **ContactManager.Mvc.wpp.targets**)，然後按一下  **新增**。</span><span class="sxs-lookup"><span data-stu-id="c6767-160">In the **Name** box, type *[project name]***.wpp.targets** (for example, **ContactManager.Mvc.wpp.targets**), and then click **Add**.</span></span>

    ![](excluding-files-and-folders-from-deployment/_static/image3.png)

    > [!NOTE]
    > <span data-ttu-id="c6767-161">如果您將新的項目加入專案的根節點時，檔案會建立專案檔相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="c6767-161">If you add a new item to the root node of a project, the file is created in the same folder as the project file.</span></span> <span data-ttu-id="c6767-162">您可以驗證，請在 Windows 檔案總管 中開啟資料夾。</span><span class="sxs-lookup"><span data-stu-id="c6767-162">You can verify this by opening the folder in Windows Explorer.</span></span>
5. <span data-ttu-id="c6767-163">在檔案中加入**專案**項目和**ItemGroup**項目：</span><span class="sxs-lookup"><span data-stu-id="c6767-163">In the file, add a **Project** element and an **ItemGroup** element:</span></span>

    [!code-xml[Main](excluding-files-and-folders-from-deployment/samples/sample2.xml)]
6. <span data-ttu-id="c6767-164">如果您想要排除資料夾從 web 封裝，加入**ExcludeFromPackageFolders**元素**ItemGroup**項目：</span><span class="sxs-lookup"><span data-stu-id="c6767-164">If you want to exclude folders from the web package, add an **ExcludeFromPackageFolders** element to the **ItemGroup** element:</span></span>

    1. <span data-ttu-id="c6767-165">在**Include**屬性，請提供您想要排除的資料夾以分號分隔清單。</span><span class="sxs-lookup"><span data-stu-id="c6767-165">In the **Include** attribute, provide a semicolon-separated list of the folders you want to exclude.</span></span>
    2. <span data-ttu-id="c6767-166">在**FromTarget**中繼資料元素，提供有意義的值，指出為什麼資料夾已被排除，如名稱*。 wpp.targets*檔案。</span><span class="sxs-lookup"><span data-stu-id="c6767-166">In the **FromTarget** metadata element, provide a meaningful value to indicate why the folders are being excluded, like the name of the *.wpp.targets* file.</span></span>

    [!code-xml[Main](excluding-files-and-folders-from-deployment/samples/sample3.xml)]
7. <span data-ttu-id="c6767-167">如果您想要排除的檔案從 web 封裝，加入**ExcludeFromPackageFiles**元素**ItemGroup**項目：</span><span class="sxs-lookup"><span data-stu-id="c6767-167">If you want to exclude files from the web package, add an **ExcludeFromPackageFiles** element to the **ItemGroup** element:</span></span>

    1. <span data-ttu-id="c6767-168">在**Include**屬性，請提供您想要排除的檔案以分號分隔清單。</span><span class="sxs-lookup"><span data-stu-id="c6767-168">In the **Include** attribute, provide a semicolon-separated list of the files you want to exclude.</span></span>
    2. <span data-ttu-id="c6767-169">在**FromTarget**中繼資料元素，提供有意義的值，指出檔案會被排除原因，如名稱*。 wpp.targets*檔案。</span><span class="sxs-lookup"><span data-stu-id="c6767-169">In the **FromTarget** metadata element, provide a meaningful value to indicate why the files are being excluded, like the name of the *.wpp.targets* file.</span></span>

    [!code-xml[Main](excluding-files-and-folders-from-deployment/samples/sample4.xml)]
8. <span data-ttu-id="c6767-170">*[專案名稱].wpp.targets*檔現在應該類似這樣：</span><span class="sxs-lookup"><span data-stu-id="c6767-170">The *[project name].wpp.targets* file should now resemble this:</span></span>

    [!code-xml[Main](excluding-files-and-folders-from-deployment/samples/sample5.xml)]
9. <span data-ttu-id="c6767-171">儲存並關閉*[專案名稱].wpp.targets*檔案。</span><span class="sxs-lookup"><span data-stu-id="c6767-171">Save and close the *[project name].wpp.targets* file.</span></span>

<span data-ttu-id="c6767-172">下次當您建置並封裝您的 web 應用程式專案，WPP 會自動偵測*。 wpp.targets*檔案。</span><span class="sxs-lookup"><span data-stu-id="c6767-172">The next time you build and package your web application project, the WPP will automatically detect the *.wpp.targets* file.</span></span> <span data-ttu-id="c6767-173">任何檔案和您指定的資料夾不會包含 web 套件中。</span><span class="sxs-lookup"><span data-stu-id="c6767-173">Any files and folders you specified will not be included in the web package.</span></span>

## <a name="conclusion"></a><span data-ttu-id="c6767-174">結論</span><span class="sxs-lookup"><span data-stu-id="c6767-174">Conclusion</span></span>

<span data-ttu-id="c6767-175">本主題描述如何排除特定檔案和資料夾，當您建立自訂建置 web 封裝， *。 wpp.targets*與您的 web 應用程式專案檔相同的資料夾中的檔案。</span><span class="sxs-lookup"><span data-stu-id="c6767-175">This topic described how to exclude specific files and folders when you build a web package, by creating a custom *.wpp.targets* file in the same folder as your web application project file.</span></span>

## <a name="further-reading"></a><span data-ttu-id="c6767-176">進一步閱讀</span><span class="sxs-lookup"><span data-stu-id="c6767-176">Further Reading</span></span>

<span data-ttu-id="c6767-177">如需有關如何使用自訂的 Microsoft Build Engine (MSBuild) 專案檔來控制部署程序的詳細資訊，請參閱[了解專案檔](../web-deployment-in-the-enterprise/understanding-the-project-file.md)和[瞭解建置程序](../web-deployment-in-the-enterprise/understanding-the-build-process.md)。</span><span class="sxs-lookup"><span data-stu-id="c6767-177">For more information on using custom Microsoft Build Engine (MSBuild) project files to control the deployment process, see [Understanding the Project File](../web-deployment-in-the-enterprise/understanding-the-project-file.md) and [Understanding the Build Process](../web-deployment-in-the-enterprise/understanding-the-build-process.md).</span></span> <span data-ttu-id="c6767-178">如需有關封裝和部署程序的詳細資訊，請參閱[建置和封裝 Web 應用程式專案](../web-deployment-in-the-enterprise/building-and-packaging-web-application-projects.md)， [Web 封裝部署的設定參數](../web-deployment-in-the-enterprise/configuring-parameters-for-web-package-deployment.md)，和[部署 Web 封裝](../web-deployment-in-the-enterprise/deploying-web-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="c6767-178">For more information on the packaging and deployment process, see [Building and Packaging Web Application Projects](../web-deployment-in-the-enterprise/building-and-packaging-web-application-projects.md), [Configuring Parameters for Web Package Deployment](../web-deployment-in-the-enterprise/configuring-parameters-for-web-package-deployment.md), and [Deploying Web Packages](../web-deployment-in-the-enterprise/deploying-web-packages.md).</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="c6767-179">[上一頁](deploying-membership-databases-to-enterprise-environments.md)
[下一頁](taking-web-applications-offline-with-web-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="c6767-179">[Previous](deploying-membership-databases-to-enterprise-environments.md)
[Next](taking-web-applications-offline-with-web-deploy.md)</span></span>