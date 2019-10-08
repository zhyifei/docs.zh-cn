---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 8f4e415576562885c9edbd3d2dddbe2a271e9923
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005466"
---
# <a name="-libpath"></a><span data-ttu-id="3b58a-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="3b58a-102">-libpath</span></span>
<span data-ttu-id="3b58a-103">指定引用程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="3b58a-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b58a-104">语法</span><span class="sxs-lookup"><span data-stu-id="3b58a-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="3b58a-105">参数</span><span class="sxs-lookup"><span data-stu-id="3b58a-105">Arguments</span></span>  
  
|<span data-ttu-id="3b58a-106">术语</span><span class="sxs-lookup"><span data-stu-id="3b58a-106">Term</span></span>|<span data-ttu-id="3b58a-107">定义</span><span class="sxs-lookup"><span data-stu-id="3b58a-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="3b58a-108">必需。</span><span class="sxs-lookup"><span data-stu-id="3b58a-108">Required.</span></span> <span data-ttu-id="3b58a-109">以分号分隔的目录列表，如果在当前工作目录（从中调用编译器的目录）或公共语言运行时的系统目录中找不到引用的程序集，则编译器将在该列表中查找。</span><span class="sxs-lookup"><span data-stu-id="3b58a-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="3b58a-110">如果目录名称包含空格，则将该名称括在引号（""）中。</span><span class="sxs-lookup"><span data-stu-id="3b58a-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b58a-111">备注</span><span class="sxs-lookup"><span data-stu-id="3b58a-111">Remarks</span></span>  
 <span data-ttu-id="3b58a-112">@No__t-0 选项指定由[-reference](../../../visual-basic/reference/command-line-compiler/reference.md)选项引用的程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="3b58a-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="3b58a-113">编译器按以下顺序搜索未完全限定的程序集引用：</span><span class="sxs-lookup"><span data-stu-id="3b58a-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="3b58a-114">当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="3b58a-114">Current working directory.</span></span> <span data-ttu-id="3b58a-115">该目录为从其调用编译器的目录。</span><span class="sxs-lookup"><span data-stu-id="3b58a-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="3b58a-116">公共语言运行时系统目录。</span><span class="sxs-lookup"><span data-stu-id="3b58a-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="3b58a-117">@No__t 指定的目录。</span><span class="sxs-lookup"><span data-stu-id="3b58a-117">Directories specified by `/libpath`.</span></span>  
  
4. <span data-ttu-id="3b58a-118">由 LIB 环境变量指定的目录。</span><span class="sxs-lookup"><span data-stu-id="3b58a-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="3b58a-119">@No__t-0 选项是累加的;多次指定它会追加到以前的任何值。</span><span class="sxs-lookup"><span data-stu-id="3b58a-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="3b58a-120">使用 `-reference` 可指定程序集引用。</span><span class="sxs-lookup"><span data-stu-id="3b58a-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="3b58a-121">在 Visual Studio 集成开发环境中设置/libpath</span><span class="sxs-lookup"><span data-stu-id="3b58a-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="3b58a-122">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="3b58a-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3b58a-123">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="3b58a-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="3b58a-124">2.单击“引用”选项卡。</span><span class="sxs-lookup"><span data-stu-id="3b58a-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="3b58a-125">3.单击 "**引用路径 ...** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="3b58a-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="3b58a-126">4.在 "**引用路径**" 对话框中，在 "**文件夹：** " 框中输入目录名称。</span><span class="sxs-lookup"><span data-stu-id="3b58a-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="3b58a-127">5.单击 "**添加文件夹**"。</span><span class="sxs-lookup"><span data-stu-id="3b58a-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3b58a-128">示例</span><span class="sxs-lookup"><span data-stu-id="3b58a-128">Example</span></span>  
 <span data-ttu-id="3b58a-129">下面的代码编译 `T2.vb` 以创建 .exe 文件。</span><span class="sxs-lookup"><span data-stu-id="3b58a-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="3b58a-130">编译器将在工作目录中的 C：驱动器的根目录中查找，并在 C：驱动器的新程序集目录中查找程序集引用。</span><span class="sxs-lookup"><span data-stu-id="3b58a-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b58a-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b58a-131">See also</span></span>

- [<span data-ttu-id="3b58a-132">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="3b58a-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="3b58a-133">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="3b58a-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3b58a-134">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="3b58a-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
