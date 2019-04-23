---
title: 此单实例应用程序未能连接到原始实例
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 7ffa9b185e16cfdf8223ce84e77d1a0e1fa67f65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322649"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="bb2ef-102">此单实例应用程序未能连接到原始实例</span><span class="sxs-lookup"><span data-stu-id="bb2ef-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="bb2ef-103">此单实例应用程序未能连接到原始实例。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="bb2ef-104">一些可能导致此问题的原因包括：</span><span class="sxs-lookup"><span data-stu-id="bb2ef-104">Some of the possible causes for this problem are as follows:</span></span>  
  
-   <span data-ttu-id="bb2ef-105">原始实例停止了响应。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-105">The original instance stopped responding.</span></span>  
  
-   <span data-ttu-id="bb2ef-106">应用程序没有创建内核对象的权限。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="bb2ef-107">有关内核对象的详细信息，请参阅[Mutex](../../standard/threading/mutexes.md)。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-107">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="bb2ef-108">内核对象的基名称是通过串联程序集的 GUID、主版本号和次版本号得到的。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="bb2ef-109">例如，基名称可能是 `3639f15d-9547-43da-8145-60da347829915.1`。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="bb2ef-110">在开发应用程序时更正此错误</span><span class="sxs-lookup"><span data-stu-id="bb2ef-110">To correct this error when developing the application</span></span>  
  
1. <span data-ttu-id="bb2ef-111">检查应用程序未进入未响应状态。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2. <span data-ttu-id="bb2ef-112">检查应用程序是否具有创建内核对象的足够权限。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3. <span data-ttu-id="bb2ef-113">重启应用程序的原始实例。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-113">Restart the original instance of the application.</span></span>  
  
4. <span data-ttu-id="bb2ef-114">重启计算机，以清除可能正在使用连接到原始实例应用程序所需资源的任何进程。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5. <span data-ttu-id="bb2ef-115">记录发生错误的环境，并与 Microsoft 产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="bb2ef-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2ef-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb2ef-116">See also</span></span>

- [<span data-ttu-id="bb2ef-117">调试器基础知识</span><span class="sxs-lookup"><span data-stu-id="bb2ef-117">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
