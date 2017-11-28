---
title: "-lib（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /lib
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 476bc43987b5ac8fa222b767b068a9ca14537bc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lib-c-compiler-options"></a><span data-ttu-id="73ec9-102">/lib（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="73ec9-102">/lib (C# Compiler Options)</span></span>
<span data-ttu-id="73ec9-103">/Lib 选项指定通过 [/reference（C# 编译器选项）](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)选项引用的程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="73ec9-103">The **/lib** option specifies the location of assemblies referenced by means of the [/reference (C# Compiler Options)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73ec9-104">语法</span><span class="sxs-lookup"><span data-stu-id="73ec9-104">Syntax</span></span>  
  
```console  
/lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="73ec9-105">参数</span><span class="sxs-lookup"><span data-stu-id="73ec9-105">Arguments</span></span>  
 `dir1`  
 <span data-ttu-id="73ec9-106">在当前工作目录（调用编译器的目录）或公共语言运行时的系统目录中未找到引用的程序集时，编译器将在其中进行查找的目录。</span><span class="sxs-lookup"><span data-stu-id="73ec9-106">A directory for the compiler to look in if a referenced assembly is not found in the current working directory (the directory from which you are invoking the compiler) or in the common language runtime's system directory.</span></span>  
  
 `dir2`  
 <span data-ttu-id="73ec9-107">要在其中搜索程序集引用的一个或多个附加目录。</span><span class="sxs-lookup"><span data-stu-id="73ec9-107">One or more additional directories to search in for assembly references.</span></span> <span data-ttu-id="73ec9-108">用逗号分隔每个附加目录的名称，中间不要有空格。</span><span class="sxs-lookup"><span data-stu-id="73ec9-108">Separate additional directory names with a comma, and without white space between them.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73ec9-109">备注</span><span class="sxs-lookup"><span data-stu-id="73ec9-109">Remarks</span></span>  
 <span data-ttu-id="73ec9-110">编译器按以下顺序搜索未完全限定的程序集引用：</span><span class="sxs-lookup"><span data-stu-id="73ec9-110">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="73ec9-111">当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="73ec9-111">Current working directory.</span></span> <span data-ttu-id="73ec9-112">该目录为从其调用编译器的目录。</span><span class="sxs-lookup"><span data-stu-id="73ec9-112">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="73ec9-113">公共语言运行时系统目录。</span><span class="sxs-lookup"><span data-stu-id="73ec9-113">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="73ec9-114">由 /lib 指定的目录。</span><span class="sxs-lookup"><span data-stu-id="73ec9-114">Directories specified by **/lib**.</span></span>  
  
4.  <span data-ttu-id="73ec9-115">由 LIB 环境变量指定的目录。</span><span class="sxs-lookup"><span data-stu-id="73ec9-115">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="73ec9-116">使用 /reference 指定程序集引用。</span><span class="sxs-lookup"><span data-stu-id="73ec9-116">Use **/reference** to specify an assembly reference.</span></span>  
  
 <span data-ttu-id="73ec9-117">/lib 是累加的；每一次指定的值都追加到以前的值中。</span><span class="sxs-lookup"><span data-stu-id="73ec9-117">**/lib** is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="73ec9-118">另一种使用 /lib 的方法是，将任何所需的程序集复制到工作目录中；这样可以仅将程序集名称传递给 /reference。</span><span class="sxs-lookup"><span data-stu-id="73ec9-118">An alternative to using **/lib** is to copy into the working directory any required assemblies; this will allow you to simply pass the assembly name to **/reference**.</span></span> <span data-ttu-id="73ec9-119">然后可以从工作目录中删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="73ec9-119">You can then delete the assemblies from the working directory.</span></span> <span data-ttu-id="73ec9-120">由于程序集清单中未指定依赖程序集的路径，因此应用程序可以在目标计算机上启动，然后查找并使用全局程序集缓存中的程序集。</span><span class="sxs-lookup"><span data-stu-id="73ec9-120">Since the path to the dependent assembly is not specified in the assembly manifest, the application can be started on the target computer and will find and use the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="73ec9-121">编译器可以引用程序集并不表示公共语言运行时可以在运行时找到并加载程序集。</span><span class="sxs-lookup"><span data-stu-id="73ec9-121">Because the compiler can reference the assembly does not imply the common language runtime will be able to find and load the assembly at runtime.</span></span> <span data-ttu-id="73ec9-122">有关运行时如何搜索引用的程序集的详细信息，请参阅[运行时如何定位程序集](../../../framework/deployment/how-the-runtime-locates-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="73ec9-122">See [How the Runtime Locates Assemblies](../../../framework/deployment/how-the-runtime-locates-assemblies.md) for details on how the runtime searches for referenced assemblies.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="73ec9-123">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="73ec9-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="73ec9-124">打开项目的“属性页”  对话框。</span><span class="sxs-lookup"><span data-stu-id="73ec9-124">Open the project's **Property Pages** dialog box.</span></span>  
  
2.  <span data-ttu-id="73ec9-125">单击“引用路径”属性页。</span><span class="sxs-lookup"><span data-stu-id="73ec9-125">Click the **References Path** property page.</span></span>  
  
3.  <span data-ttu-id="73ec9-126">修改列表框的内容。</span><span class="sxs-lookup"><span data-stu-id="73ec9-126">Modify the contents of the list box.</span></span>  
  
 <span data-ttu-id="73ec9-127">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>。</span><span class="sxs-lookup"><span data-stu-id="73ec9-127">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73ec9-128">示例</span><span class="sxs-lookup"><span data-stu-id="73ec9-128">Example</span></span>  
 <span data-ttu-id="73ec9-129">编译 t2.cs 以创建 .exe 文件。</span><span class="sxs-lookup"><span data-stu-id="73ec9-129">Compile t2.cs to create an .exe file.</span></span> <span data-ttu-id="73ec9-130">编译器将在工作目录和 C 驱动器的根目录中查找程序集引用。</span><span class="sxs-lookup"><span data-stu-id="73ec9-130">The compiler will look in the working directory and in the root directory of the C drive for assembly references.</span></span>  
  
```console  
csc /lib:c:\ /reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="73ec9-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73ec9-131">See Also</span></span>  
 [<span data-ttu-id="73ec9-132">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="73ec9-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="73ec9-133">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="73ec9-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
