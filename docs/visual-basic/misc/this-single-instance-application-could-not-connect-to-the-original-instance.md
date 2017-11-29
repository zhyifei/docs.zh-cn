---
title: "此单实例应用程序未能连接到原始实例"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fbc8458231c36f3af9ca4de524e01e19a162ee47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="85847-102">此单实例应用程序未能连接到原始实例</span><span class="sxs-lookup"><span data-stu-id="85847-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="85847-103">此单实例应用程序未能连接到原始实例。</span><span class="sxs-lookup"><span data-stu-id="85847-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="85847-104">一些可能导致此问题的原因包括：</span><span class="sxs-lookup"><span data-stu-id="85847-104">Some of the possible causes for this problem are as follows:</span></span>  
  
-   <span data-ttu-id="85847-105">原始实例停止了响应。</span><span class="sxs-lookup"><span data-stu-id="85847-105">The original instance stopped responding.</span></span>  
  
-   <span data-ttu-id="85847-106">应用程序没有创建内核对象的权限。</span><span class="sxs-lookup"><span data-stu-id="85847-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="85847-107">有关内核对象的详细信息，请参阅[互斥体](../../standard/threading/mutexes.md)。</span><span class="sxs-lookup"><span data-stu-id="85847-107">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="85847-108">内核对象的基名称是通过串联程序集的 GUID、主版本号和次版本号得到的。</span><span class="sxs-lookup"><span data-stu-id="85847-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="85847-109">例如，基名称可能是 `3639f15d-9547-43da-8145-60da347829915.1`。</span><span class="sxs-lookup"><span data-stu-id="85847-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="85847-110">在开发应用程序时更正此错误</span><span class="sxs-lookup"><span data-stu-id="85847-110">To correct this error when developing the application</span></span>  
  
1.  <span data-ttu-id="85847-111">检查应用程序未进入未响应状态。</span><span class="sxs-lookup"><span data-stu-id="85847-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2.  <span data-ttu-id="85847-112">检查应用程序是否具有创建内核对象的足够权限。</span><span class="sxs-lookup"><span data-stu-id="85847-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3.  <span data-ttu-id="85847-113">重启应用程序的原始实例。</span><span class="sxs-lookup"><span data-stu-id="85847-113">Restart the original instance of the application.</span></span>  
  
4.  <span data-ttu-id="85847-114">重启计算机，以清除可能正在使用连接到原始实例应用程序所需资源的任何进程。</span><span class="sxs-lookup"><span data-stu-id="85847-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5.  <span data-ttu-id="85847-115">记录发生错误的环境，并与 Microsoft 产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="85847-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85847-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85847-116">See Also</span></span>  
 [<span data-ttu-id="85847-117">NIB： 如何： 指定应用程序 (Visual Basic) 的实例化行为</span><span class="sxs-lookup"><span data-stu-id="85847-117">NIB: How to: Specify Instancing Behavior for an Application (Visual Basic)</span></span>](http://msdn.microsoft.com/en-us/48539ad8-d960-4210-beab-ee65f6c6dc6e)  
 [<span data-ttu-id="85847-118">调试器基础知识</span><span class="sxs-lookup"><span data-stu-id="85847-118">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)  
 [<span data-ttu-id="85847-119">PAVEOVER 产品支持和辅助功能</span><span class="sxs-lookup"><span data-stu-id="85847-119">PAVEOVER Product Support and Accessibility</span></span>](http://msdn.microsoft.com/en-us/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)
