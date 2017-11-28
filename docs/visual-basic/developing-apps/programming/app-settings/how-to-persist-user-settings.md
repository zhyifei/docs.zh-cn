---
title: "如何：在 Visual Basic 中保存用户设置"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e1cf424a4e587818a8e2766a5e27c084010c084c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a><span data-ttu-id="ae026-102">如何：在 Visual Basic 中保存用户设置</span><span class="sxs-lookup"><span data-stu-id="ae026-102">How to: Persist User Settings in Visual Basic</span></span>
<span data-ttu-id="ae026-103">可以使用 `My.Settings.Save` 方法来保存对用户设置的更改。</span><span class="sxs-lookup"><span data-stu-id="ae026-103">You can use the `My.Settings.Save` method to persist changes to the user settings.</span></span>  
  
 <span data-ttu-id="ae026-104">通常情况下，将应用程序设计为在应用程序关闭时保存用户设置的更改。</span><span class="sxs-lookup"><span data-stu-id="ae026-104">Typically, applications are designed to persist the changes to the user settings when the application shuts down.</span></span> <span data-ttu-id="ae026-105">这是因为保存设置需要几秒钟，具体取决于多种因素。</span><span class="sxs-lookup"><span data-stu-id="ae026-105">This is because saving the settings can take, depending on several factors, several seconds.</span></span>  
  
 <span data-ttu-id="ae026-106">有关详细信息，请参阅 [My.Settings 对象](../../../../visual-basic/language-reference/objects/my-settings-object.md)。</span><span class="sxs-lookup"><span data-stu-id="ae026-106">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae026-107">虽然可以在运行时更改并保存用户范围设置的值，但是应用程序范围设置是只读的，不能以编程方式进行更改。</span><span class="sxs-lookup"><span data-stu-id="ae026-107">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="ae026-108">可以在创建应用程序时通过**项目设计器**，或者编辑应用程序的配置文件来更改应用程序范围设置。</span><span class="sxs-lookup"><span data-stu-id="ae026-108">You can change application-scope settings when creating the application, through the **Project Designer**, or by editing the application's configuration file.</span></span> <span data-ttu-id="ae026-109">有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="ae026-109">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae026-110">示例</span><span class="sxs-lookup"><span data-stu-id="ae026-110">Example</span></span>  
 <span data-ttu-id="ae026-111">本示例更改 `LastChanged` 用户设置的值，并通过调用 `My.Settings.Save` 方法来保存此更改。</span><span class="sxs-lookup"><span data-stu-id="ae026-111">This example changes the value of the `LastChanged` user setting and saves that change by calling the `My.Settings.Save` method.</span></span>  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]  
  
 <span data-ttu-id="ae026-112">若要使用本示例，应用程序必须具有类型为 `Date` 的 `LastChanged` 用户设置。</span><span class="sxs-lookup"><span data-stu-id="ae026-112">For this example to work, your application must have a `LastChanged` user setting, of type `Date`.</span></span> <span data-ttu-id="ae026-113">有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="ae026-113">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae026-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae026-114">See Also</span></span>  
 [<span data-ttu-id="ae026-115">My.Settings 对象</span><span class="sxs-lookup"><span data-stu-id="ae026-115">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="ae026-116">如何：在 Visual Basic 中读取应用程序设置</span><span class="sxs-lookup"><span data-stu-id="ae026-116">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [<span data-ttu-id="ae026-117">如何：在 Visual Basic 中更改用户设置</span><span class="sxs-lookup"><span data-stu-id="ae026-117">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [<span data-ttu-id="ae026-118">如何：在 Visual Basic 中创建用户设置的属性网格</span><span class="sxs-lookup"><span data-stu-id="ae026-118">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [<span data-ttu-id="ae026-119">管理应用程序设置 (.NET)</span><span class="sxs-lookup"><span data-stu-id="ae026-119">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
