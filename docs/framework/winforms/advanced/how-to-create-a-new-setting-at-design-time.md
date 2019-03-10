---
title: 如何：在设计时创建新的设置
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: 54f64de8cdd47b7fd451d266cca3b7577e9e1d78
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702771"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="bacb4-102">如何：在设计时创建新的设置</span><span class="sxs-lookup"><span data-stu-id="bacb4-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="bacb4-103">使用设置设计器，可以在设计时创建一个新的设置。</span><span class="sxs-lookup"><span data-stu-id="bacb4-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="bacb4-104">设置设计器是一个网格样式接口，可用于创建新的设置，并指定这些设置的属性。</span><span class="sxs-lookup"><span data-stu-id="bacb4-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="bacb4-105">必须指定名称、 值、 类型和新的设置的作用域。</span><span class="sxs-lookup"><span data-stu-id="bacb4-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="bacb4-106">一旦创建了设置，就可在代码中访问。</span><span class="sxs-lookup"><span data-stu-id="bacb4-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="bacb4-107">若要在设计时在 C 中创建新的设置\#</span><span class="sxs-lookup"><span data-stu-id="bacb4-107">To create a new setting at design time in C\#</span></span>
  
1.  <span data-ttu-id="bacb4-108">在中**解决方案资源管理器**，展开**属性**在项目节点。</span><span class="sxs-lookup"><span data-stu-id="bacb4-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2.  <span data-ttu-id="bacb4-109">双击想要添加新设置.settings 文件。</span><span class="sxs-lookup"><span data-stu-id="bacb4-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="bacb4-110">此文件的默认名称是 Settings.settings。</span><span class="sxs-lookup"><span data-stu-id="bacb4-110">The default name for this file is Settings.settings.</span></span>  
  
3.  <span data-ttu-id="bacb4-111">在设置设计器中，设置名称、 值、 类型和您的设置的作用域。</span><span class="sxs-lookup"><span data-stu-id="bacb4-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="bacb4-112">每行代表单个设置。</span><span class="sxs-lookup"><span data-stu-id="bacb4-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="bacb4-113">若要在设计时在 Visual Basic 中创建一个新的设置</span><span class="sxs-lookup"><span data-stu-id="bacb4-113">To create a new setting at design time in Visual Basic</span></span>  
  
1.  <span data-ttu-id="bacb4-114">在中**解决方案资源管理器**，右键单击项目节点并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="bacb4-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="bacb4-115">在中**属性**页上，选择**设置**选项卡。</span><span class="sxs-lookup"><span data-stu-id="bacb4-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3.  <span data-ttu-id="bacb4-116">在设置设计器中，设置名称、 值、 类型和您的设置的作用域。</span><span class="sxs-lookup"><span data-stu-id="bacb4-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="bacb4-117">每行代表单个设置。</span><span class="sxs-lookup"><span data-stu-id="bacb4-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bacb4-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="bacb4-118">See also</span></span>
- [<span data-ttu-id="bacb4-119">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="bacb4-119">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="bacb4-120">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="bacb4-120">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="bacb4-121">如何：在设计时的现有设置的值更改</span><span class="sxs-lookup"><span data-stu-id="bacb4-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
