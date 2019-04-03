---
title: 类型“<typename1>”的值无法转换为“<typename2>”
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 5f313a43bc3a2f983dabbd45477d120fdb80d063
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829014"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a><span data-ttu-id="bb08b-102">类型的值\<typename1 > 无法转换为\<typename2 ></span><span class="sxs-lookup"><span data-stu-id="bb08b-102">Value of type '\<typename1>' cannot be converted to '\<typename2>'</span></span>
<span data-ttu-id="bb08b-103">类型的值\<typename1 > 无法转换为\<typename2 >。</span><span class="sxs-lookup"><span data-stu-id="bb08b-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="bb08b-104">类型不匹配可能是由于的文件引用的程序集的项目引用混合使用\<程序集名称 >。</span><span class="sxs-lookup"><span data-stu-id="bb08b-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="bb08b-105">请尝试更换的文件引用\<文件路径 > 项目中\<projectname1 > 项目引用\<项目名称 2> >。</span><span class="sxs-lookup"><span data-stu-id="bb08b-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="bb08b-106">在其中一个项目会的项目引用和文件引用的情况下，编译器无法保证一个类型可转换为另一个。</span><span class="sxs-lookup"><span data-stu-id="bb08b-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="bb08b-107">下面的伪代码说明了可能会生成此错误的情况。</span><span class="sxs-lookup"><span data-stu-id="bb08b-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
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
  
 <span data-ttu-id="bb08b-108">项目`P1`完成项目间接的项目引用`P2`到项目`P3`，同时还对直接文件引用`P3`。</span><span class="sxs-lookup"><span data-stu-id="bb08b-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="bb08b-109">声明`commonObject`使用的文件引用`P3`，而在调用`P2.getCommonClass`将使用到的项目引用`P3`。</span><span class="sxs-lookup"><span data-stu-id="bb08b-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="bb08b-110">在此情况下的问题是文件引用指定的文件路径和名称的输出文件`P3`(通常为 p3.dll)，而项目引用标识源项目 (`P3`) 按项目名称。</span><span class="sxs-lookup"><span data-stu-id="bb08b-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="bb08b-111">因此，编译器无法保证该类型`P3.commonClass`来自通过两个不同的引用相同的源代码。</span><span class="sxs-lookup"><span data-stu-id="bb08b-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="bb08b-112">这种情况通常发生在项目引用和文件引用混合。</span><span class="sxs-lookup"><span data-stu-id="bb08b-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="bb08b-113">在上图中，会出现问题如果`P1`进行直接的项目引用到`P3`而不是文件引用。</span><span class="sxs-lookup"><span data-stu-id="bb08b-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="bb08b-114">**错误 ID:** BC30955</span><span class="sxs-lookup"><span data-stu-id="bb08b-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bb08b-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bb08b-115">To correct this error</span></span>  
  
-   <span data-ttu-id="bb08b-116">更改的项目引用的文件引用。</span><span class="sxs-lookup"><span data-stu-id="bb08b-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb08b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb08b-117">See also</span></span>

- [<span data-ttu-id="bb08b-118">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="bb08b-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="bb08b-119">管理项目中的引用</span><span class="sxs-lookup"><span data-stu-id="bb08b-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
