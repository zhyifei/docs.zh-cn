---
title: "/nostdlib (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
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
ms.openlocfilehash: 046e2b845324ed1c2f8c15bbb029fe84f7693f6e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="nostdlib-visual-basic"></a><span data-ttu-id="49773-102">/nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49773-102">/nostdlib (Visual Basic)</span></span>
<span data-ttu-id="49773-103">使编译器不会自动引用标准库。</span><span class="sxs-lookup"><span data-stu-id="49773-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49773-104">语法</span><span class="sxs-lookup"><span data-stu-id="49773-104">Syntax</span></span>  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="49773-105">备注</span><span class="sxs-lookup"><span data-stu-id="49773-105">Remarks</span></span>  
 <span data-ttu-id="49773-106">`/nostdlib`选项删除对 System.dll 程序集的自动引用，可防止编译器读取 Vbc.rsp 文件。</span><span class="sxs-lookup"><span data-stu-id="49773-106">The `/nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="49773-107">Vbc.rsp 文件 — — 位于 Vbc.exe 文件所在的同一个目录 — 引用常用[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]程序集和导入`System`和`Microsoft.VisualBasic`命名空间。</span><span class="sxs-lookup"><span data-stu-id="49773-107">The Vbc.rsp file—which is located in the same directory as the Vbc.exe file—references the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49773-108">始终引用 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的程序集。</span><span class="sxs-lookup"><span data-stu-id="49773-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49773-109">`/nostdlib`选项不是在 Visual Studio 开发环境中可用; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="49773-109">The `/nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49773-110">示例</span><span class="sxs-lookup"><span data-stu-id="49773-110">Example</span></span>  
 <span data-ttu-id="49773-111">下面的代码编译`T2.vb`而不引用标准库。</span><span class="sxs-lookup"><span data-stu-id="49773-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="49773-112">必须设置`_MYTYPE`为字符串"空"若要删除的条件编译常数`My`对象。</span><span class="sxs-lookup"><span data-stu-id="49773-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="49773-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49773-113">See Also</span></span>  
 <span data-ttu-id="49773-114">[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="49773-114">[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="49773-115"> [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="49773-115"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="49773-116"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="49773-116"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="49773-117"> [自定义 My 中可用的对象](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)</span><span class="sxs-lookup"><span data-stu-id="49773-117"> [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)</span></span>
