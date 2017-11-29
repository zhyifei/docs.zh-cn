---
title: "如何：向应用程序添加多个设置组 (C#)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec541a8f83990eec79226be7fb4880ef8dda639d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="755bc-102">如何：向应用程序添加多个设置组 (C#)</span><span class="sxs-lookup"><span data-stu-id="755bc-102">How To: Add Multiple Sets of Settings To Your Application in C#</span></span> #
<span data-ttu-id="755bc-103">在某些情况下，你可能想要在应用程序具有多个集的设置。</span><span class="sxs-lookup"><span data-stu-id="755bc-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="755bc-104">例如，如果你正在开发的应用一组特定的设置需要经常更改，它可能是明智的做法是将它们分开所有导入到单个文件，以便该文件可以替换整个，使其他设置不受影响。</span><span class="sxs-lookup"><span data-stu-id="755bc-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="755bc-105">Visual Studio 允许你将多组设置添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="755bc-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="755bc-106">可以通过 Properties.Settings 对象访问设置的其他集。</span><span class="sxs-lookup"><span data-stu-id="755bc-106">Additional sets of settings can be accessed via the Properties.Settings object.</span></span>  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a><span data-ttu-id="755bc-107">将一组额外的设置添加到你的应用程序</span><span class="sxs-lookup"><span data-stu-id="755bc-107">To Add an Additional Set of Setting to your Application</span></span>  
  
1.  <span data-ttu-id="755bc-108">从“项目”菜单中选择“添加新项”。</span><span class="sxs-lookup"><span data-stu-id="755bc-108">From the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="755bc-109">此时将打开“添加新项”对话框。</span><span class="sxs-lookup"><span data-stu-id="755bc-109">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="755bc-110">在**添加新项**对话框中，选择**设置文件**，键入，为文件的名称，然后单击**添加**将新的设置文件添加到你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="755bc-110">In the **Add New Item** dialog box, select **Settings File**, type in a name for the file, and click **Add** to add a new settings file to your solution.</span></span>  
  
3.  <span data-ttu-id="755bc-111">在**解决方案资源管理器**，拖动到新的设置文件**属性**文件夹。</span><span class="sxs-lookup"><span data-stu-id="755bc-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="755bc-112">这允许你设置可在代码中使用新设置。</span><span class="sxs-lookup"><span data-stu-id="755bc-112">This allows your new settings to be available in code.</span></span>  
  
4.  <span data-ttu-id="755bc-113">添加和使用此文件中的设置，就像任何其他设置文件。</span><span class="sxs-lookup"><span data-stu-id="755bc-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="755bc-114">你可以访问此组通过 Properties.Settings 对象的设置。</span><span class="sxs-lookup"><span data-stu-id="755bc-114">You can access this group of settings via the Properties.Settings object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="755bc-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="755bc-115">See Also</span></span>  
 [<span data-ttu-id="755bc-116">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="755bc-116">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="755bc-117">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="755bc-117">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
