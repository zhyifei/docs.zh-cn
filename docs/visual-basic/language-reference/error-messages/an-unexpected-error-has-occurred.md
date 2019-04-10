---
title: 发生错误，因为无法获得单个实例启动所需的操作系统资源
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 9aa7ba0babe0a89942e320a76e07c05162b31700
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313601"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="d5de9-102">发生错误，因为无法获得单个实例启动所需的操作系统资源</span><span class="sxs-lookup"><span data-stu-id="d5de9-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="d5de9-103">应用程序未能获取所需的操作系统资源。</span><span class="sxs-lookup"><span data-stu-id="d5de9-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="d5de9-104">一些可能导致此问题的原因是：</span><span class="sxs-lookup"><span data-stu-id="d5de9-104">Some of the possible causes for this problem are:</span></span>  
  
-   <span data-ttu-id="d5de9-105">应用程序不具备创建命名操作系统对象的权限。</span><span class="sxs-lookup"><span data-stu-id="d5de9-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
-   <span data-ttu-id="d5de9-106">公共语言运行时不具备创建内存映射文件的权限。</span><span class="sxs-lookup"><span data-stu-id="d5de9-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
-   <span data-ttu-id="d5de9-107">应用程序需要访问某个操作系统对象，但另一个进程正在使用该对象。</span><span class="sxs-lookup"><span data-stu-id="d5de9-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d5de9-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d5de9-108">To correct this error</span></span>  
  
1. <span data-ttu-id="d5de9-109">检查该应用程序具有创建命名操作系统对象的足够权限。</span><span class="sxs-lookup"><span data-stu-id="d5de9-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2. <span data-ttu-id="d5de9-110">检查公共语言运行时具有创建内存映射文件的足够权限。</span><span class="sxs-lookup"><span data-stu-id="d5de9-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3. <span data-ttu-id="d5de9-111">重新启动计算机以清除可能正使用连接到原始实例应用程序所需的资源的任何进程。</span><span class="sxs-lookup"><span data-stu-id="d5de9-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4. <span data-ttu-id="d5de9-112">记录发生错误的环境，并与 Microsoft 产品支持服务联系</span><span class="sxs-lookup"><span data-stu-id="d5de9-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5de9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5de9-113">See also</span></span>

- [<span data-ttu-id="d5de9-114">Application Page, Project Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5de9-114">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="d5de9-115">调试器基础知识</span><span class="sxs-lookup"><span data-stu-id="d5de9-115">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
- [<span data-ttu-id="d5de9-116">Talk to Us</span><span class="sxs-lookup"><span data-stu-id="d5de9-116">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
