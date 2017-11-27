---
title: "使用 My.Resources 和 My.Settings 快速开发应用程序 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1657febf935560ff4c8dd2f54b10fdcb2254891f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="f5876-102">使用 My.Resources 和 My.Settings 快速开发应用程序 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5876-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="f5876-103">`My.Resources`对象提供对应用程序的资源的访问，并允许你动态检索应用程序资源。</span><span class="sxs-lookup"><span data-stu-id="f5876-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="f5876-104">检索资源</span><span class="sxs-lookup"><span data-stu-id="f5876-104">Retrieving Resources</span></span>  
 <span data-ttu-id="f5876-105">可以通过检索大量资源，例如音频文件、 图标、 图像和字符串`My.Resources`对象。</span><span class="sxs-lookup"><span data-stu-id="f5876-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="f5876-106">例如，你可以访问应用程序的区域性特定资源文件。</span><span class="sxs-lookup"><span data-stu-id="f5876-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="f5876-107">下面的示例设置窗体的图标名为的图标`Form1Icon`存储在应用程序的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f5876-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 <span data-ttu-id="f5876-108">`My.Resources`对象公开仅全局资源。</span><span class="sxs-lookup"><span data-stu-id="f5876-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="f5876-109">它不提供对与窗体关联的资源文件的访问。</span><span class="sxs-lookup"><span data-stu-id="f5876-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="f5876-110">必须从窗体来访问窗体资源。</span><span class="sxs-lookup"><span data-stu-id="f5876-110">You must access the form resources from the form.</span></span> <span data-ttu-id="f5876-111">有关详细信息，请参阅[演练：本地化 Windows 窗体](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)。</span><span class="sxs-lookup"><span data-stu-id="f5876-111">For more information, see [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).</span></span>  
  
 <span data-ttu-id="f5876-112">同样，`My.Settings`对象提供对应用程序的设置访问权限和可以动态存储和检索属性设置以及你的应用程序的其他信息。</span><span class="sxs-lookup"><span data-stu-id="f5876-112">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="f5876-113">有关详细信息，请参阅[My.Resources 对象](../../../visual-basic/language-reference/objects/my-resources-object.md)和[My.Settings 对象](../../../visual-basic/language-reference/objects/my-settings-object.md)。</span><span class="sxs-lookup"><span data-stu-id="f5876-113">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5876-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5876-114">See Also</span></span>  
 [<span data-ttu-id="f5876-115">My.Resources 对象</span><span class="sxs-lookup"><span data-stu-id="f5876-115">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [<span data-ttu-id="f5876-116">My.Settings 对象</span><span class="sxs-lookup"><span data-stu-id="f5876-116">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="f5876-117">访问应用程序设置</span><span class="sxs-lookup"><span data-stu-id="f5876-117">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
