---
title: "类型的值 &quot;&lt;typename1，而&gt;无法转换为&lt;typename2&gt;&quot; |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
dev_langs:
- VB
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
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
ms.openlocfilehash: 2fbe1550515d2b15a3e349392fc8d78812787ae4
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a><span data-ttu-id="ddcd8-102">类型的值 '&lt;typename1，而&gt;无法转换为&lt;typename2&gt;</span><span class="sxs-lookup"><span data-stu-id="ddcd8-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="ddcd8-103">类型的值 '\<typename1，而&1;> 不能转换为\<typename2&1;>。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="ddcd8-104">类型不匹配可能是由于混合的文件引用与程序集的项目引用\<程序集名称&1;>。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="ddcd8-105">请尝试替换为文件引用和对\<filepath&1;> 在项目中\<projectname1&1;> 到的项目引用\<projectname2&1;>。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="ddcd8-106">在其中一个项目使项目引用和文件引用的情况下，编译器不能保证可将一种类型转换为另一个。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="ddcd8-107">下面的伪代码说明了可能会产生此错误的情况。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="ddcd8-108">项目`P1`间接的项目引用了通过项目`P2`到项目`P3`，同时还对直接文件引用`P3`。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="ddcd8-109">声明`commonObject`使用文件引用和对`P3`，而对调用`P2.getCommonClass`中使用项目引用`P3`。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="ddcd8-110">这种情况下的问题是文件引用指定的文件路径和名称的输出文件`P3`(通常为 p3.dll)，而项目引用标识源项目 (`P3`) 按项目名称。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="ddcd8-111">因此，编译器也不能保证该类型`P3.commonClass`来自通过两个不同的引用相同的源代码。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="ddcd8-112">这种情况通常发生在项目引用和混合的文件引用。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="ddcd8-113">在上图中，此问题不会发生如果`P1`进行直接的项目引用到`P3`而不是引用的文件。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="ddcd8-114">**错误 ID:** BC30955</span><span class="sxs-lookup"><span data-stu-id="ddcd8-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ddcd8-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ddcd8-115">To correct this error</span></span>  
  
-   <span data-ttu-id="ddcd8-116">更改对项目引用的文件引用。</span><span class="sxs-lookup"><span data-stu-id="ddcd8-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddcd8-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddcd8-117">See Also</span></span>  
 <span data-ttu-id="ddcd8-118">[在 Visual Basic 中的类型转换](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="ddcd8-118">[Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="ddcd8-119"> [管理项目中引用](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="ddcd8-119"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="ddcd8-120"> [NIB 如何：使用“添加引用”对话框添加或删除引用](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span><span class="sxs-lookup"><span data-stu-id="ddcd8-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span></span>
