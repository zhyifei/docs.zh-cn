---
title: "访问应用程序窗体 (Visual Basic)"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- forms, communicating between
- application forms, accessing
- forms, accessing one from another
- My.Forms object
- forms, accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 37c8aa78d945a4d13ce00239d6b0707977f2571e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="73717-102">访问应用程序窗体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73717-102">Accessing Application Forms (Visual Basic)</span></span>
<span data-ttu-id="73717-103">`My.Forms` 对象提供一种简单方法，用于访问在应用程序项目中声明的每个 Windows 窗体的实例。</span><span class="sxs-lookup"><span data-stu-id="73717-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="73717-104">还可以使用 `My.Application` 对象的属性来访问应用程序的初始屏幕和主窗体，并获取应用程序的打开的窗体的列表。</span><span class="sxs-lookup"><span data-stu-id="73717-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="73717-105">任务</span><span class="sxs-lookup"><span data-stu-id="73717-105">Tasks</span></span>  
 <span data-ttu-id="73717-106">下表列出了演示如何访问应用程序窗体的示例。</span><span class="sxs-lookup"><span data-stu-id="73717-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="73717-107">到</span><span class="sxs-lookup"><span data-stu-id="73717-107">To</span></span>|<span data-ttu-id="73717-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="73717-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="73717-109">在应用程序中从某一窗体访问另一窗体。</span><span class="sxs-lookup"><span data-stu-id="73717-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="73717-110">My.Forms 对象</span><span class="sxs-lookup"><span data-stu-id="73717-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="73717-111">显示应用程序所有打开的窗体的标题。</span><span class="sxs-lookup"><span data-stu-id="73717-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="73717-112">在应用程序启动时，使用状态信息更新初始屏幕。</span><span class="sxs-lookup"><span data-stu-id="73717-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="73717-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73717-113">See Also</span></span>  
 <span data-ttu-id="73717-114"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A></span><span class="sxs-lookup"><span data-stu-id="73717-114"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A></span></span>   
 <span data-ttu-id="73717-115"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A></span><span class="sxs-lookup"><span data-stu-id="73717-115"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A></span></span>   
 [<span data-ttu-id="73717-116">My.Forms 对象</span><span class="sxs-lookup"><span data-stu-id="73717-116">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)

