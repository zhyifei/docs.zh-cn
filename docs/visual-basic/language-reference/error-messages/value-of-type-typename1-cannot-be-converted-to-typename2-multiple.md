---
title: "类型的值 &quot;&lt;typename1，而&gt;无法转换为&lt;typename2&gt;（多个文件引用） |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
dev_langs:
- VB
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
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
ms.openlocfilehash: 299cc4bec00a4597a661c5da49135fe3b5357537
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="d30d9-102">类型的值 '&lt;typename1，而&gt;无法转换为&lt;typename2&gt;（多个文件引用）</span><span class="sxs-lookup"><span data-stu-id="d30d9-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="d30d9-103">类型的值 '\<typename1，而&1;> 不能转换为\<typename2&1;>。</span><span class="sxs-lookup"><span data-stu-id="d30d9-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="d30d9-104">类型不匹配可能是由于混合使用引用的文件\<filepath1&1;> 在项目中\<projectname1&1;> 文件引用和对\<filepath2&1;> 在项目中\<projectname2&1;>。</span><span class="sxs-lookup"><span data-stu-id="d30d9-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="d30d9-105">如果两个程序集完全相同，请尝试更换这些引用，以确保两个引用都来自相同的位置。</span><span class="sxs-lookup"><span data-stu-id="d30d9-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="d30d9-106">在其中项目进行的程序集的多个文件引用的情况下，编译器不能保证可将一种类型转换为另一个。</span><span class="sxs-lookup"><span data-stu-id="d30d9-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="d30d9-107">每个文件引用指定文件路径和一个项目 （通常为 DLL 文件） 的输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d30d9-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="d30d9-108">编译器无法保证输出文件来自同一源，或者它们是否表示同一个程序集的相同版本。</span><span class="sxs-lookup"><span data-stu-id="d30d9-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="d30d9-109">因此，它不能保证中不同的引用的类型是相同的类型，或甚至一个可以转换为其他。</span><span class="sxs-lookup"><span data-stu-id="d30d9-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="d30d9-110">如果您知道所引用的程序集具有相同的程序集标识，可以使用单个文件引用。</span><span class="sxs-lookup"><span data-stu-id="d30d9-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="d30d9-111">*程序集标识* 包括程序集的名称、版本、公钥（如果有）和区域性。</span><span class="sxs-lookup"><span data-stu-id="d30d9-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="d30d9-112">此信息唯一地标识该程序集。</span><span class="sxs-lookup"><span data-stu-id="d30d9-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="d30d9-113">**错误 ID:** BC30961</span><span class="sxs-lookup"><span data-stu-id="d30d9-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d30d9-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d30d9-114">To correct this error</span></span>  
  
-   <span data-ttu-id="d30d9-115">如果引用的程序集具有相同的程序集标识，然后删除或替换其中的一个文件引用，以便只有单个文件引用。</span><span class="sxs-lookup"><span data-stu-id="d30d9-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="d30d9-116">如果引用的程序集不具有相同的程序集标识，然后更改您的代码，以便不会尝试转换为类型在另一个中的类型。</span><span class="sxs-lookup"><span data-stu-id="d30d9-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d30d9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d30d9-117">See Also</span></span>  
 <span data-ttu-id="d30d9-118">[在 Visual Basic 中的类型转换](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="d30d9-118">[Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="d30d9-119"> [管理项目中引用](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="d30d9-119"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="d30d9-120"> [NIB 如何：使用“添加引用”对话框添加或删除引用](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span><span class="sxs-lookup"><span data-stu-id="d30d9-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span></span>
