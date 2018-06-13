---
title: 类型的值&#39; &lt;typename1&gt; &#39;不能转换为&#39; &lt;typename2&gt; &#39; （多个文件引用）
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 41c18160be9b546f8b525376fa06bc0eca6c117a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603686"
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="f4b4d-102">类型的值&#39; &lt;typename1&gt; &#39;不能转换为&#39; &lt;typename2&gt; &#39; （多个文件引用）</span><span class="sxs-lookup"><span data-stu-id="f4b4d-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="f4b4d-103">类型的值\<typename1 > 不能转换为\<typename2 >。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="f4b4d-104">类型不匹配可能是由于混合对的文件引用\<h 1 > 项目中\<projectname1 > 对的文件引用与\<h 2 > 项目中\<项目名称 2> >。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="f4b4d-105">如果两个程序集完全相同，请尝试更换这些引用，以确保两个引用都来自相同的位置。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="f4b4d-106">其中一个项目使多个文件引用的程序集的情况下，编译器不能保证一个类型可转换为另一个。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="f4b4d-107">每个文件引用指定的文件路径和名称的项目 （通常为 DLL 文件） 的输出文件。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="f4b4d-108">编译器无法保证输出文件来自同一源，或它们表示同一程序集的相同的版本。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="f4b4d-109">因此，它不能保证不同的引用中的类型具有相同的类型，或甚至一个可以转换为其他。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="f4b4d-110">如果你知道引用的程序集具有相同的程序集标识，你可以使用的单个文件引用。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="f4b4d-111">*程序集标识* 包括程序集的名称、版本、公钥（如果有）和区域性。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="f4b4d-112">此信息唯一地标识该程序集。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="f4b4d-113">**错误 ID:** BC30961</span><span class="sxs-lookup"><span data-stu-id="f4b4d-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f4b4d-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f4b4d-114">To correct this error</span></span>  
  
-   <span data-ttu-id="f4b4d-115">如果被引用程序集具有相同的程序集标识，然后删除或替换其中的一个文件引用，以便只有单个文件引用。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="f4b4d-116">如果引用的程序集不具有相同的程序集标识，然后更改你的代码，以便它不会尝试转换到另一部分中的类型中的类型。</span><span class="sxs-lookup"><span data-stu-id="f4b4d-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b4d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4b4d-117">See Also</span></span>  
 [<span data-ttu-id="f4b4d-118">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="f4b4d-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="f4b4d-119">管理项目中的引用</span><span class="sxs-lookup"><span data-stu-id="f4b4d-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 
