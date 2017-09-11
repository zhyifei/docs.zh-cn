---
title: "My.Settings 对象 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4d6ee6d2d54c0e3a4af3b7cdec5f81166ce3ddce
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="mysettings-object"></a><span data-ttu-id="ea816-102">My.Settings 对象</span><span class="sxs-lookup"><span data-stu-id="ea816-102">My.Settings Object</span></span>
<span data-ttu-id="ea816-103">提供属性和方法来访问应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="ea816-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea816-104">备注</span><span class="sxs-lookup"><span data-stu-id="ea816-104">Remarks</span></span>  
 <span data-ttu-id="ea816-105">`My.Settings`对象提供对应用程序的设置的访问，并允许您动态地存储和检索属性设置和您的应用程序的其他信息。</span><span class="sxs-lookup"><span data-stu-id="ea816-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="ea816-106">有关详细信息，请参阅[管理应用程序设置 (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="ea816-106">For more information, see [Managing Application Settings (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ea816-107">属性</span><span class="sxs-lookup"><span data-stu-id="ea816-107">Properties</span></span>  
 <span data-ttu-id="ea816-108">属性的`My.Settings`对象提供对应用程序的设置的访问。</span><span class="sxs-lookup"><span data-stu-id="ea816-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="ea816-109">若要添加或删除设置，请使用**设置设计器**。</span><span class="sxs-lookup"><span data-stu-id="ea816-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="ea816-110">每个设置具有**名称**，**类型**，**范围**，和**值**，并且这些设置确定用于访问每个设置的属性中的显示方式`My.Settings`对象︰</span><span class="sxs-lookup"><span data-stu-id="ea816-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="ea816-111">**名称**确定该属性的名称。</span><span class="sxs-lookup"><span data-stu-id="ea816-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="ea816-112">**类型**确定该属性的类型。</span><span class="sxs-lookup"><span data-stu-id="ea816-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="ea816-113">**作用域**指示属性是否是只读的。</span><span class="sxs-lookup"><span data-stu-id="ea816-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="ea816-114">如果值为**应用程序**，该属性是只读的; 如果值为**用户**，该属性是可读写。</span><span class="sxs-lookup"><span data-stu-id="ea816-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="ea816-115">**值**是属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="ea816-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea816-116">方法</span><span class="sxs-lookup"><span data-stu-id="ea816-116">Methods</span></span>  
  
|<span data-ttu-id="ea816-117">方法</span><span class="sxs-lookup"><span data-stu-id="ea816-117">Method</span></span>|<span data-ttu-id="ea816-118">描述</span><span class="sxs-lookup"><span data-stu-id="ea816-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="ea816-119">重新加载上次保存的值中的用户设置。</span><span class="sxs-lookup"><span data-stu-id="ea816-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="ea816-120">将保存当前的用户设置。</span><span class="sxs-lookup"><span data-stu-id="ea816-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="ea816-121">`My.Settings`对象还提供了高级的属性和方法，继承<xref:System.Configuration.ApplicationSettingsBase>类。</xref:System.Configuration.ApplicationSettingsBase></span><span class="sxs-lookup"><span data-stu-id="ea816-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="ea816-122">任务</span><span class="sxs-lookup"><span data-stu-id="ea816-122">Tasks</span></span>  
 <span data-ttu-id="ea816-123">下表列出了所涉及的任务的示例`My.Settings`对象。</span><span class="sxs-lookup"><span data-stu-id="ea816-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="ea816-124">到</span><span class="sxs-lookup"><span data-stu-id="ea816-124">To</span></span>|<span data-ttu-id="ea816-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea816-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="ea816-126">读取应用程序设置</span><span class="sxs-lookup"><span data-stu-id="ea816-126">Read an application setting</span></span>|[<span data-ttu-id="ea816-127">如何︰ 读取在 Visual Basic 中的应用程序设置</span><span class="sxs-lookup"><span data-stu-id="ea816-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="ea816-128">更改用户设置</span><span class="sxs-lookup"><span data-stu-id="ea816-128">Change a user setting</span></span>|[<span data-ttu-id="ea816-129">如何︰ 在 Visual Basic 中的用户设置更改</span><span class="sxs-lookup"><span data-stu-id="ea816-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="ea816-130">保持用户设置</span><span class="sxs-lookup"><span data-stu-id="ea816-130">Persist user settings</span></span>|[<span data-ttu-id="ea816-131">如何︰ 保存在 Visual Basic 中的用户设置</span><span class="sxs-lookup"><span data-stu-id="ea816-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="ea816-132">创建用户设置的属性网格</span><span class="sxs-lookup"><span data-stu-id="ea816-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="ea816-133">如何︰ 创建在 Visual Basic 中的用户设置的属性网格</span><span class="sxs-lookup"><span data-stu-id="ea816-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="ea816-134">示例</span><span class="sxs-lookup"><span data-stu-id="ea816-134">Example</span></span>  
 <span data-ttu-id="ea816-135">此示例中显示的值`Nickname`设置。</span><span class="sxs-lookup"><span data-stu-id="ea816-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 <span data-ttu-id="ea816-136">[!code-vb[VbVbalrMyResources #&14;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ea816-136">[!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]</span></span>  
  
 <span data-ttu-id="ea816-137">对于此示例正常工作，您的应用程序必须具有`Nickname`类型设置`String`。</span><span class="sxs-lookup"><span data-stu-id="ea816-137">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea816-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea816-138">See Also</span></span>  
 <span data-ttu-id="ea816-139"><xref:System.Configuration.ApplicationSettingsBase></xref:System.Configuration.ApplicationSettingsBase></span><span class="sxs-lookup"><span data-stu-id="ea816-139"><xref:System.Configuration.ApplicationSettingsBase></span></span>   
<span data-ttu-id="ea816-140"> [如何︰ 读取在 Visual Basic 中的应用程序设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="ea816-140"> [How to: Read Application Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
<span data-ttu-id="ea816-141"> [如何︰ 在 Visual Basic 中的用户设置更改](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="ea816-141"> [How to: Change User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
<span data-ttu-id="ea816-142"> [如何︰ 保存在 Visual Basic 中的用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="ea816-142"> [How to: Persist User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
<span data-ttu-id="ea816-143"> [如何︰ 创建在 Visual Basic 中的用户设置的属性网格](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="ea816-143"> [How to: Create Property Grids for User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
<span data-ttu-id="ea816-144"> [管理应用程序设置 (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)</span><span class="sxs-lookup"><span data-stu-id="ea816-144"> [Managing Application Settings (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)</span></span>
