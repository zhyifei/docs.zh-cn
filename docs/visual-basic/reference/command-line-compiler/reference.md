---
title: -参考 (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 2394a23ddd59d09ce53c78fc4486fc5bae9e8516
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583356"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="ae202-102">-参考 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae202-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="ae202-103">使编译器让指定程序集中的类型信息供当前正在编译的项目。</span><span class="sxs-lookup"><span data-stu-id="ae202-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae202-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae202-104">Syntax</span></span>  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae202-105">自变量</span><span class="sxs-lookup"><span data-stu-id="ae202-105">Arguments</span></span>  
  
|<span data-ttu-id="ae202-106">术语</span><span class="sxs-lookup"><span data-stu-id="ae202-106">Term</span></span>|<span data-ttu-id="ae202-107">定义</span><span class="sxs-lookup"><span data-stu-id="ae202-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="ae202-108">必需。</span><span class="sxs-lookup"><span data-stu-id="ae202-108">Required.</span></span> <span data-ttu-id="ae202-109">程序集文件名的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="ae202-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="ae202-110">如果文件名包含空格，则将名称括在引号内。</span><span class="sxs-lookup"><span data-stu-id="ae202-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae202-111">备注</span><span class="sxs-lookup"><span data-stu-id="ae202-111">Remarks</span></span>  
 <span data-ttu-id="ae202-112">导入的文件必须包含程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="ae202-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="ae202-113">仅公共类型都是程序集外部可见的。</span><span class="sxs-lookup"><span data-stu-id="ae202-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="ae202-114">[/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)选项从模块导入元数据。</span><span class="sxs-lookup"><span data-stu-id="ae202-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="ae202-115">如果引用的程序集 （程序集 A） 本身引用了另一个程序集 (程序集 B)，则在下列情况下需要引用程序集 B:</span><span class="sxs-lookup"><span data-stu-id="ae202-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="ae202-116">程序集 A 中的类型继承自程序集 B 中的类型或实现程序集 B 中的接口。</span><span class="sxs-lookup"><span data-stu-id="ae202-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="ae202-117">调用具有程序集 B 中的返回类型或参数类型的字段、属性、事件或方法。</span><span class="sxs-lookup"><span data-stu-id="ae202-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="ae202-118">使用[-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)指定一个或多个程序集引用所在的目录。</span><span class="sxs-lookup"><span data-stu-id="ae202-118">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="ae202-119">为使编译器可以识别的程序集 （而不是模块） 中的类型，必须强制其解析的类型。</span><span class="sxs-lookup"><span data-stu-id="ae202-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="ae202-120">如何执行此操作的一个示例是定义类型的实例。</span><span class="sxs-lookup"><span data-stu-id="ae202-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="ae202-121">其他方法都可以解析为编译器的程序集中的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ae202-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="ae202-122">例如，如果您从程序集中的类型继承，类型名称然后将成为编译器已知。</span><span class="sxs-lookup"><span data-stu-id="ae202-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="ae202-123">默认情况下使用 Vbc.rsp 响应文件，通常使用.NET Framework 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="ae202-123">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="ae202-124">使用`-noconfig`如果不希望编译器使用 Vbc.rsp。</span><span class="sxs-lookup"><span data-stu-id="ae202-124">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="ae202-125">`-reference` 的缩写形式是 `/r`。</span><span class="sxs-lookup"><span data-stu-id="ae202-125">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae202-126">示例</span><span class="sxs-lookup"><span data-stu-id="ae202-126">Example</span></span>  
 <span data-ttu-id="ae202-127">下面的命令编译源文件`Input.vb`和引用程序集从`Metad1.dll`并`Metad2.dll`以生成`Out.exe`。</span><span class="sxs-lookup"><span data-stu-id="ae202-127">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae202-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae202-128">See also</span></span>

- [<span data-ttu-id="ae202-129">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="ae202-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ae202-130">-noconfig</span><span class="sxs-lookup"><span data-stu-id="ae202-130">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="ae202-131">-目标 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae202-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="ae202-132">Public</span><span class="sxs-lookup"><span data-stu-id="ae202-132">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="ae202-133">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="ae202-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
