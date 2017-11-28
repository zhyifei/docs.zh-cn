---
title: "如何：在 Visual Basic 中更改用户设置"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: db35a5d63938fcc508c23af5588957d8dc518676
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-user-settings-in-visual-basic"></a><span data-ttu-id="36001-102">如何：在 Visual Basic 中更改用户设置</span><span class="sxs-lookup"><span data-stu-id="36001-102">How to: Change User Settings in Visual Basic</span></span>
<span data-ttu-id="36001-103">可以通过将新值赋予 `My.Settings` 对象上的设置属性来更改用户设置。</span><span class="sxs-lookup"><span data-stu-id="36001-103">You can change a user setting by assigning a new value to the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="36001-104">`My.Settings` 对象将每个设置公开为一个属性。</span><span class="sxs-lookup"><span data-stu-id="36001-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="36001-105">属性名称就是设置的名称，属性类型就是设置类型。</span><span class="sxs-lookup"><span data-stu-id="36001-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="36001-106">设置的“范围”决定属性是否为只读；“应用程序”范围设置的属性是只读属性，而“用户”范围设置的属性是读-写属性。</span><span class="sxs-lookup"><span data-stu-id="36001-106">The setting's **Scope** determines if the property is read-only: The property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="36001-107">有关详细信息，请参阅 [My.Settings 对象](../../../../visual-basic/language-reference/objects/my-settings-object.md)。</span><span class="sxs-lookup"><span data-stu-id="36001-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36001-108">虽然可以在运行时更改并保存用户范围设置的值，但是应用程序范围设置是只读的，不能以编程方式进行更改。</span><span class="sxs-lookup"><span data-stu-id="36001-108">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="36001-109">可以在创建应用程序时通过“项目设计器”，或者编辑应用程序的配置文件来更改应用程序范围设置。</span><span class="sxs-lookup"><span data-stu-id="36001-109">You can change application-scope settings when you create the application by using the **Project Designer** or by editing the application's configuration file.</span></span> <span data-ttu-id="36001-110">有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="36001-110">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="36001-111">示例</span><span class="sxs-lookup"><span data-stu-id="36001-111">Example</span></span>  
 <span data-ttu-id="36001-112">此示例更改 `Nickname` 用户设置的值。</span><span class="sxs-lookup"><span data-stu-id="36001-112">This example changes the value of the `Nickname` user setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]  
  
 <span data-ttu-id="36001-113">若要使用本示例，应用程序必须具有类型为 `String` 的 `Nickname` 用户设置。</span><span class="sxs-lookup"><span data-stu-id="36001-113">For this example to work, your application must have a `Nickname` user setting, of type `String`.</span></span>  
  
 <span data-ttu-id="36001-114">应用程序在关闭时会保存用户设置。</span><span class="sxs-lookup"><span data-stu-id="36001-114">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="36001-115">若要立即保存设置，请调用 `My.Settings.Save` 方法。</span><span class="sxs-lookup"><span data-stu-id="36001-115">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="36001-116">有关详细信息，请参阅[如何：在 Visual Basic 中保存用户设置](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="36001-116">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36001-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36001-117">See Also</span></span>  
 [<span data-ttu-id="36001-118">My.Settings 对象</span><span class="sxs-lookup"><span data-stu-id="36001-118">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="36001-119">如何：在 Visual Basic 中读取应用程序设置</span><span class="sxs-lookup"><span data-stu-id="36001-119">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [<span data-ttu-id="36001-120">如何：在 Visual Basic 中保存用户设置</span><span class="sxs-lookup"><span data-stu-id="36001-120">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="36001-121">如何：在 Visual Basic 中创建用户设置的属性网格</span><span class="sxs-lookup"><span data-stu-id="36001-121">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [<span data-ttu-id="36001-122">管理应用程序设置 (.NET)</span><span class="sxs-lookup"><span data-stu-id="36001-122">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
