---
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 8b57affa05c77d8ed20bfead7de767a8dd994241
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348582"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="ac499-102">-reference （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="ac499-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="ac499-103">使编译器使指定程序集中的类型信息可供当前正在编译的项目使用。</span><span class="sxs-lookup"><span data-stu-id="ac499-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac499-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac499-104">Syntax</span></span>  
  
```console  
-reference:fileList  
```

<span data-ttu-id="ac499-105">或</span><span class="sxs-lookup"><span data-stu-id="ac499-105">or</span></span>

```console
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac499-106">参数</span><span class="sxs-lookup"><span data-stu-id="ac499-106">Arguments</span></span>  
  
|<span data-ttu-id="ac499-107">术语</span><span class="sxs-lookup"><span data-stu-id="ac499-107">Term</span></span>|<span data-ttu-id="ac499-108">Definition</span><span class="sxs-lookup"><span data-stu-id="ac499-108">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="ac499-109">必需。</span><span class="sxs-lookup"><span data-stu-id="ac499-109">Required.</span></span> <span data-ttu-id="ac499-110">程序集文件名的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="ac499-110">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="ac499-111">如果文件名包含空格，则将名称括在引号内。</span><span class="sxs-lookup"><span data-stu-id="ac499-111">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac499-112">备注</span><span class="sxs-lookup"><span data-stu-id="ac499-112">Remarks</span></span>  
 <span data-ttu-id="ac499-113">导入的文件必须包含程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="ac499-113">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="ac499-114">仅公共类型在程序集外可见。</span><span class="sxs-lookup"><span data-stu-id="ac499-114">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="ac499-115">[-Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)选项从模块导入元数据。</span><span class="sxs-lookup"><span data-stu-id="ac499-115">The [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="ac499-116">如果引用本身引用另一个程序集（程序集 B）的程序集（程序集 A），则需要在以下情况下引用程序集 B：</span><span class="sxs-lookup"><span data-stu-id="ac499-116">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="ac499-117">程序集 A 中的类型继承自程序集 B 中的类型或实现程序集 B 中的接口。</span><span class="sxs-lookup"><span data-stu-id="ac499-117">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="ac499-118">调用具有程序集 B 中的返回类型或参数类型的字段、属性、事件或方法。</span><span class="sxs-lookup"><span data-stu-id="ac499-118">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="ac499-119">使用[-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)可指定一个或多个程序集引用所在的目录。</span><span class="sxs-lookup"><span data-stu-id="ac499-119">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="ac499-120">为了使编译器能够识别程序集中的类型（而不是模块），必须强制解析该类型。</span><span class="sxs-lookup"><span data-stu-id="ac499-120">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="ac499-121">如何执行此操作的一个示例是定义类型的实例。</span><span class="sxs-lookup"><span data-stu-id="ac499-121">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="ac499-122">其他方法可用于解析编译器的程序集中的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ac499-122">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="ac499-123">例如，如果从程序集中的某个类型继承，则该类型名称将在编译器中是已知的。</span><span class="sxs-lookup"><span data-stu-id="ac499-123">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="ac499-124">默认情况下，将使用用于引用常用 .NET Framework 程序集的 Vbc 响应文件。</span><span class="sxs-lookup"><span data-stu-id="ac499-124">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="ac499-125">如果你不希望编译器使用 Vbc，请使用 `-noconfig`。</span><span class="sxs-lookup"><span data-stu-id="ac499-125">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="ac499-126">`-reference` 的缩写形式是 `/r`。</span><span class="sxs-lookup"><span data-stu-id="ac499-126">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac499-127">示例</span><span class="sxs-lookup"><span data-stu-id="ac499-127">Example</span></span>  
 <span data-ttu-id="ac499-128">以下命令将源文件 `Input.vb` 和引用程序集从 `Metad1.dll` 和 `Metad2.dll` 编译为生成 `Out.exe`。</span><span class="sxs-lookup"><span data-stu-id="ac499-128">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac499-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac499-129">See also</span></span>

- [<span data-ttu-id="ac499-130">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="ac499-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ac499-131">-noconfig</span><span class="sxs-lookup"><span data-stu-id="ac499-131">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="ac499-132">-target （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="ac499-132">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="ac499-133">Public</span><span class="sxs-lookup"><span data-stu-id="ac499-133">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="ac499-134">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="ac499-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
