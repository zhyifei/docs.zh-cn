---
title: "/reference (Visual Basic 中) |Microsoft 文档"
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
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6870c0b6008124bad18f8eba9207d06e085f2307
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="reference-visual-basic"></a><span data-ttu-id="f95fd-102">/reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f95fd-102">/reference (Visual Basic)</span></span>
<span data-ttu-id="f95fd-103">使编译器将在指定的程序集的类型信息提供给当前正在编译项目。</span><span class="sxs-lookup"><span data-stu-id="f95fd-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f95fd-104">语法</span><span class="sxs-lookup"><span data-stu-id="f95fd-104">Syntax</span></span>  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="f95fd-105">参数</span><span class="sxs-lookup"><span data-stu-id="f95fd-105">Arguments</span></span>  
  
|<span data-ttu-id="f95fd-106">术语</span><span class="sxs-lookup"><span data-stu-id="f95fd-106">Term</span></span>|<span data-ttu-id="f95fd-107">定义</span><span class="sxs-lookup"><span data-stu-id="f95fd-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="f95fd-108">必需。</span><span class="sxs-lookup"><span data-stu-id="f95fd-108">Required.</span></span> <span data-ttu-id="f95fd-109">程序集文件名称的以逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="f95fd-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="f95fd-110">如果文件名包含空格，则将名称括在引号内。</span><span class="sxs-lookup"><span data-stu-id="f95fd-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f95fd-111">备注</span><span class="sxs-lookup"><span data-stu-id="f95fd-111">Remarks</span></span>  
 <span data-ttu-id="f95fd-112">在导入的文件必须包含程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="f95fd-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="f95fd-113">仅将公共类型是在程序集外部可见的。</span><span class="sxs-lookup"><span data-stu-id="f95fd-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="f95fd-114">[/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)选项从模块导入元数据。</span><span class="sxs-lookup"><span data-stu-id="f95fd-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="f95fd-115">如果引用的程序集 （程序集 A） 其本身引用另一个程序集 (程序集 B)，如果需要引用程序集 B:</span><span class="sxs-lookup"><span data-stu-id="f95fd-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="f95fd-116">程序集 A 中的类型继承自的类型或实现程序集 B 中的接口</span><span class="sxs-lookup"><span data-stu-id="f95fd-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="f95fd-117">字段、 属性、 事件或程序集 B 中的返回类型或形参类型的方法被调用。</span><span class="sxs-lookup"><span data-stu-id="f95fd-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="f95fd-118">使用[/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)若要指定一个或多个程序集引用所在的目录。</span><span class="sxs-lookup"><span data-stu-id="f95fd-118">Use [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="f95fd-119">编译器无法识别出的程序集 （而不是模块） 的类型，必须将它强制要解析的类型。</span><span class="sxs-lookup"><span data-stu-id="f95fd-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="f95fd-120">如何执行此操作的一个示例是定义类型的实例。</span><span class="sxs-lookup"><span data-stu-id="f95fd-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="f95fd-121">其他方法是可用于解析编译器的程序集中的类型名称。</span><span class="sxs-lookup"><span data-stu-id="f95fd-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="f95fd-122">例如，如果您从程序集中的类型继承，类型名称则将成为已知给编译器。</span><span class="sxs-lookup"><span data-stu-id="f95fd-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="f95fd-123">Vbc.rsp 响应文件引用常用[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]程序集，默认情况下使用。</span><span class="sxs-lookup"><span data-stu-id="f95fd-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="f95fd-124">使用`/noconfig`如果不希望使用 Vbc.rsp 的编译器。</span><span class="sxs-lookup"><span data-stu-id="f95fd-124">Use `/noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="f95fd-125">缩写形式`/reference`是`/r`。</span><span class="sxs-lookup"><span data-stu-id="f95fd-125">The short form of `/reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f95fd-126">示例</span><span class="sxs-lookup"><span data-stu-id="f95fd-126">Example</span></span>  
 <span data-ttu-id="f95fd-127">下面的代码编译源代码文件我`nput.vb`和引用程序集从 M`etad1.dll`和 M`etad2.dll`以生成 O`ut.exe`。</span><span class="sxs-lookup"><span data-stu-id="f95fd-127">The following code compiles source file I`nput.vb` and reference assemblies from M`etad1.dll` and M`etad2.dll` to produce O`ut.exe`.</span></span>  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f95fd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f95fd-128">See Also</span></span>  
 <span data-ttu-id="f95fd-129">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f95fd-129">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f95fd-130"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="f95fd-130"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="f95fd-131"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="f95fd-131"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="f95fd-132"> [公共](../../../visual-basic/language-reference/modifiers/public.md) </span><span class="sxs-lookup"><span data-stu-id="f95fd-132"> [Public](../../../visual-basic/language-reference/modifiers/public.md) </span></span>  
<span data-ttu-id="f95fd-133"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="f95fd-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
