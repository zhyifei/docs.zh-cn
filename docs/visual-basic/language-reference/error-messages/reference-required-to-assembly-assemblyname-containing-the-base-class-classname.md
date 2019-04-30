---
title: 需要对程序集“<assemblyname>”（包含基类“<classname>”）的引用
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: 54848fdbd2547fe021f0386843f9666760396cb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013772"
---
# <a name="reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a><span data-ttu-id="3d98f-102">需要对程序集的引用\<程序集名称 > 包含基类的\<类名 >'</span><span class="sxs-lookup"><span data-stu-id="3d98f-102">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'</span></span>
<span data-ttu-id="3d98f-103">需要对程序集的引用\<程序集名称 > 包含基类的\<类名 >。</span><span class="sxs-lookup"><span data-stu-id="3d98f-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="3d98f-104">请向项目中添加一个。</span><span class="sxs-lookup"><span data-stu-id="3d98f-104">Add one to your project.</span></span>  
  
 <span data-ttu-id="3d98f-105">该类是在动态链接库 (DLL) 或未在项目中直接引用的程序集中定义的。</span><span class="sxs-lookup"><span data-stu-id="3d98f-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="3d98f-106">Visual Basic 编译器需要引用以避免多义性的类定义在多个 DLL 或程序集。</span><span class="sxs-lookup"><span data-stu-id="3d98f-106">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>  
  
 <span data-ttu-id="3d98f-107">**错误 ID:** BC30007</span><span class="sxs-lookup"><span data-stu-id="3d98f-107">**Error ID:** BC30007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3d98f-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3d98f-108">To correct this error</span></span>  
  
- <span data-ttu-id="3d98f-109">将未引用的 DLL 或程序集名称包括在项目引用中。</span><span class="sxs-lookup"><span data-stu-id="3d98f-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d98f-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d98f-110">See also</span></span>

- [<span data-ttu-id="3d98f-111">管理项目中的引用</span><span class="sxs-lookup"><span data-stu-id="3d98f-111">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="3d98f-112">有关无效的引用的疑难解答</span><span class="sxs-lookup"><span data-stu-id="3d98f-112">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
