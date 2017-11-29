---
title: "访问应用程序窗体 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- forms [Visual Basic], communicating between
- application forms [Visual Basic], accessing
- forms [Visual Basic], accessing one from another
- My.Forms object
- forms [Visual Basic], accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b029ce984f9cef540087181a83070b0c8aa8132
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="c89ea-102">访问应用程序窗体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c89ea-102">Accessing Application Forms (Visual Basic)</span></span>
<span data-ttu-id="c89ea-103">`My.Forms` 对象提供一种简单方法，用于访问在应用程序项目中声明的每个 Windows 窗体的实例。</span><span class="sxs-lookup"><span data-stu-id="c89ea-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="c89ea-104">还可以使用 `My.Application` 对象的属性来访问应用程序的初始屏幕和主窗体，并获取应用程序的打开的窗体的列表。</span><span class="sxs-lookup"><span data-stu-id="c89ea-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="c89ea-105">任务</span><span class="sxs-lookup"><span data-stu-id="c89ea-105">Tasks</span></span>  
 <span data-ttu-id="c89ea-106">下表列出了演示如何访问应用程序窗体的示例。</span><span class="sxs-lookup"><span data-stu-id="c89ea-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="c89ea-107">到</span><span class="sxs-lookup"><span data-stu-id="c89ea-107">To</span></span>|<span data-ttu-id="c89ea-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="c89ea-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="c89ea-109">在应用程序中从某一窗体访问另一窗体。</span><span class="sxs-lookup"><span data-stu-id="c89ea-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="c89ea-110">My.Forms 对象</span><span class="sxs-lookup"><span data-stu-id="c89ea-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="c89ea-111">显示应用程序所有打开的窗体的标题。</span><span class="sxs-lookup"><span data-stu-id="c89ea-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="c89ea-112">在应用程序启动时，使用状态信息更新初始屏幕。</span><span class="sxs-lookup"><span data-stu-id="c89ea-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="c89ea-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c89ea-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>  
 [<span data-ttu-id="c89ea-114">My.Forms 对象</span><span class="sxs-lookup"><span data-stu-id="c89ea-114">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
