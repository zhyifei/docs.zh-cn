---
title: -target:winmdobj（C# 编译器选项）
ms.date: 07/20/2015
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
ms.openlocfilehash: 85ae9a3f5e9b038c0c56935ec5af2b9b09d19f20
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204494"
---
# <a name="-targetwinmdobj-c-compiler-options"></a><span data-ttu-id="fc1af-102">-target:winmdobj（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="fc1af-102">-target:winmdobj (C# Compiler Options)</span></span>
<span data-ttu-id="fc1af-103">如果使用 -target:winmdobj 编译器选项，则编译器会创建一个中间 .winmdobj 文件，你可以将这个文件转换为 Windows 运行时二进制 (.winmd) 文件  。</span><span class="sxs-lookup"><span data-stu-id="fc1af-103">If you use the **-target:winmdobj** compiler option, the compiler creates an intermediate .winmdobj file that you can convert to a Windows Runtime binary (.winmd) file.</span></span> <span data-ttu-id="fc1af-104">之后，除了托管语言程序外，JavaScript 和 C++ 程序也可以使用该 .winmd 文件。</span><span class="sxs-lookup"><span data-stu-id="fc1af-104">The .winmd file can then be consumed by JavaScript and C++ programs, in addition to managed language programs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc1af-105">语法</span><span class="sxs-lookup"><span data-stu-id="fc1af-105">Syntax</span></span>  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a><span data-ttu-id="fc1af-106">备注</span><span class="sxs-lookup"><span data-stu-id="fc1af-106">Remarks</span></span>  
 <span data-ttu-id="fc1af-107">**winmdobj** 设置会向编译器发出信号，表示需要中间模块。</span><span class="sxs-lookup"><span data-stu-id="fc1af-107">The **winmdobj** setting signals to the compiler that an intermediate module is required.</span></span> <span data-ttu-id="fc1af-108">作为响应，Visual Studio 会将 C# 类库编译为 .winmdobj 文件。</span><span class="sxs-lookup"><span data-stu-id="fc1af-108">In response, Visual Studio compiles the C# class library as a .winmdobj file.</span></span> <span data-ttu-id="fc1af-109">随后，.winmdobj 文件可作为可作为 <xref:Microsoft.Build.Tasks.WinMDExp> 导出工具的输入，生成 Windows 元数据 (.winmd) 文件。</span><span class="sxs-lookup"><span data-stu-id="fc1af-109">The .winmdobj file can then be fed through the <xref:Microsoft.Build.Tasks.WinMDExp> export tool to produce a Windows metadata (.winmd) file.</span></span> <span data-ttu-id="fc1af-110">.winmd 文件既包含原始库的代码，也包括 JavaScript（或 C++）以及 Windows 运行时使用的 WinMD 元数据的代码。</span><span class="sxs-lookup"><span data-stu-id="fc1af-110">The .winmd file contains both the code from the original library and the WinMD metadata that is used by JavaScript or C++ and by the Windows Runtime.</span></span>  
  
 <span data-ttu-id="fc1af-111">使用 -target:winmdobj 编译器选项所编译的文件，只能用作 WimMDExp 导出工具的输入；不能直接引用 .winmdobj 文件自身  。</span><span class="sxs-lookup"><span data-stu-id="fc1af-111">The output of a file that’s compiled by using the **-target:winmdobj** compiler option is designed to be used only as input for the WimMDExp export tool; the .winmdobj file itself isn’t referenced directly.</span></span>  
  
 <span data-ttu-id="fc1af-112">除非使用 [-out](./out-compiler-option.md) 选项，否则输出文件的名称采用第一个输入文件的名称。</span><span class="sxs-lookup"><span data-stu-id="fc1af-112">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span> <span data-ttu-id="fc1af-113">不需要使用 [Main](../../programming-guide/main-and-command-args/index.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="fc1af-113">A [Main](../../programming-guide/main-and-command-args/index.md) method isn’t required.</span></span>  
  
 <span data-ttu-id="fc1af-114">如果在命令提示符处指定 -target:winmdobj 选项，则在指定下一个 -out 或 [-target:module](./target-module-compiler-option.md) 选项之前，会使用所有文件来创建 Windows 程序  。</span><span class="sxs-lookup"><span data-stu-id="fc1af-114">If you specify the -target:winmdobj option at a command prompt, all files until the next **-out** or [-target:module](./target-module-compiler-option.md) option are used to create the Windows program.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a><span data-ttu-id="fc1af-115">在 Visual Studio IDE 中为 Windows 应用商店应用程序设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="fc1af-115">To set this compiler option in the Visual Studio IDE for a Windows Store app</span></span>  
  
1. <span data-ttu-id="fc1af-116">在“解决方案资源管理器”  中，打开项目的快捷菜单，然后选择“属性”  。</span><span class="sxs-lookup"><span data-stu-id="fc1af-116">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="fc1af-117">选择“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="fc1af-117">Choose the **Application** tab.</span></span>  
  
3. <span data-ttu-id="fc1af-118">在“输出类型”  列表中，选择“WinMD 文件”  。</span><span class="sxs-lookup"><span data-stu-id="fc1af-118">In the **Output type** list, choose **WinMD File**.</span></span>  
  
     <span data-ttu-id="fc1af-119">此“WinMD 文件”选项仅可用于 Windows 8.x 应用商店应用模板  。</span><span class="sxs-lookup"><span data-stu-id="fc1af-119">The **WinMD File** option is available only for Windows 8.x Store app templates.</span></span>  
  
 <span data-ttu-id="fc1af-120">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>。</span><span class="sxs-lookup"><span data-stu-id="fc1af-120">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc1af-121">示例</span><span class="sxs-lookup"><span data-stu-id="fc1af-121">Example</span></span>  
 <span data-ttu-id="fc1af-122">以下命令将 `filename.cs` 编译为一个中间 .winmdobj 文件。</span><span class="sxs-lookup"><span data-stu-id="fc1af-122">The following command compiles `filename.cs` into an intermediate .winmdobj file.</span></span>  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc1af-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc1af-123">See also</span></span>

- [<span data-ttu-id="fc1af-124">-target（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="fc1af-124">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="fc1af-125">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="fc1af-125">C# Compiler Options</span></span>](./index.md)
