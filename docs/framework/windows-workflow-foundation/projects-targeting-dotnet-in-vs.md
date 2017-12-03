---
title: "在 Visual Studio 2010 中编写面向 .NET Framework 3.0 和 3.5 的项目"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6dc6657bad5cc11eaa723c733319673468749b79
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="writing-projects-targeting-the-net-framework-30-and-35-in-visual-studio-2010"></a><span data-ttu-id="294c5-102">在 Visual Studio 2010 中编写面向 .NET Framework 3.0 和 3.5 的项目</span><span class="sxs-lookup"><span data-stu-id="294c5-102">Writing Projects Targeting the .NET Framework 3.0 and 3.5 in Visual Studio 2010</span></span>
<span data-ttu-id="294c5-103">可使用 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] 创建面向 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 版本 3.0 或 3.5 的项目。</span><span class="sxs-lookup"><span data-stu-id="294c5-103">You can use [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] to create projects that target the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] version 3.0 or 3.5.</span></span> <span data-ttu-id="294c5-104">本主题介绍如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="294c5-104">This topic describes how to do this.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="294c5-105">在添加活动时，请确保设置所需版本的 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="294c5-105">When adding activities, make sure that the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] is set.</span></span> <span data-ttu-id="294c5-106">在添加活动后更改工作流的目标版本将导致工作流验证失败。</span><span class="sxs-lookup"><span data-stu-id="294c5-106">Changing the target version of the workflow after activities are added will cause the workflow to fail validation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="294c5-107">在 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] 中打开具有 .Net Framework 3.5 活动的现有工作流将导致 `this.SetValue()` 出错。</span><span class="sxs-lookup"><span data-stu-id="294c5-107">Opening existing workflows in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] that have .Net Framework 3.5 activities will cause an error at `this.SetValue()`.</span></span> <span data-ttu-id="294c5-108">若要打开用早期版本的 .Net Framework 创建的项目，请先在设计器中打开一个空白工作流并添加一个 .Net Framework 3.5 活动。</span><span class="sxs-lookup"><span data-stu-id="294c5-108">In order to open projects created with previous versions of the .Net Framework, first open a blank workflow in the designer and add a .Net Framework 3.5 activity.</span></span>  
  
## <a name="to-create-a-net-framework--30-or-35-project-with-visual-studio-2010"></a><span data-ttu-id="294c5-109">使用 Visual Studio 2010 创建 .NET Framework 3.0 或 3.5 项目</span><span class="sxs-lookup"><span data-stu-id="294c5-109">To create a .NET Framework  3.0 or 3.5 project with Visual Studio 2010</span></span>  
  
1.  <span data-ttu-id="294c5-110">打开 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="294c5-110">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="294c5-111">选择**文件**，**新**，**项目**。</span><span class="sxs-lookup"><span data-stu-id="294c5-111">Select **File**, **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="294c5-112">在对话框顶部的下拉列表中，选择所需版本的 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="294c5-112">In the drop-down list at the top of the dialog box, select the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="to-upgrade-the-targeted-version-of-the-net-framework"></a><span data-ttu-id="294c5-113">升级 .NET Framework 的目标版本</span><span class="sxs-lookup"><span data-stu-id="294c5-113">To upgrade the targeted version of the .NET Framework</span></span>  
  
1.  <span data-ttu-id="294c5-114">右键单击解决方案资源管理器中的项目并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="294c5-114">Right-click the project in Solution Explorer, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="294c5-115">在**目标框架**下拉列表中，选择所需的版本。</span><span class="sxs-lookup"><span data-stu-id="294c5-115">In the **Target Framework** drop-down list, select the desired version.</span></span>
