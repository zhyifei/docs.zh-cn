---
title: "/libpath |Microsoft 文档"
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
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
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
ms.openlocfilehash: 7f24dd7707645f45677dcf7009e1adc64afaaa7c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="libpath"></a><span data-ttu-id="f820f-102">/libpath</span><span class="sxs-lookup"><span data-stu-id="f820f-102">/libpath</span></span>
<span data-ttu-id="f820f-103">指定引用的程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="f820f-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f820f-104">语法</span><span class="sxs-lookup"><span data-stu-id="f820f-104">Syntax</span></span>  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="f820f-105">参数</span><span class="sxs-lookup"><span data-stu-id="f820f-105">Arguments</span></span>  
  
|<span data-ttu-id="f820f-106">术语</span><span class="sxs-lookup"><span data-stu-id="f820f-106">Term</span></span>|<span data-ttu-id="f820f-107">定义</span><span class="sxs-lookup"><span data-stu-id="f820f-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="f820f-108">必需。</span><span class="sxs-lookup"><span data-stu-id="f820f-108">Required.</span></span> <span data-ttu-id="f820f-109">以分号分隔的编译器进行查找的引用的程序集的目录列表中未找到任何一个当前工作目录 （调用编译器的目录） 或公共语言运行时的系统目录。</span><span class="sxs-lookup"><span data-stu-id="f820f-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="f820f-110">如果目录名称包含空格，则将名称括在双引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="f820f-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f820f-111">备注</span><span class="sxs-lookup"><span data-stu-id="f820f-111">Remarks</span></span>  
 <span data-ttu-id="f820f-112">`/libpath`选项指定引用的程序集的位置[/引用](../../../visual-basic/reference/command-line-compiler/reference.md)选项。</span><span class="sxs-lookup"><span data-stu-id="f820f-112">The `/libpath` option specifies the location of assemblies referenced by the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="f820f-113">编译器将搜索未按以下顺序完全限定的程序集引用︰</span><span class="sxs-lookup"><span data-stu-id="f820f-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="f820f-114">当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="f820f-114">Current working directory.</span></span> <span data-ttu-id="f820f-115">这是从中调用编译器的目录。</span><span class="sxs-lookup"><span data-stu-id="f820f-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="f820f-116">公共语言运行时的系统目录。</span><span class="sxs-lookup"><span data-stu-id="f820f-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="f820f-117">由指定的目录`/libpath`。</span><span class="sxs-lookup"><span data-stu-id="f820f-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="f820f-118">LIB 环境变量所指定的目录。</span><span class="sxs-lookup"><span data-stu-id="f820f-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="f820f-119">`/libpath`选项是累加性; 指定其超过一次将追加到任何以前的值。</span><span class="sxs-lookup"><span data-stu-id="f820f-119">The `/libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="f820f-120">使用`/reference`来指定程序集引用。</span><span class="sxs-lookup"><span data-stu-id="f820f-120">Use `/reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="f820f-121">在 Visual Studio 中设置 /libpath 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="f820f-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="f820f-122">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="f820f-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f820f-123">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f820f-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="f820f-124">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="f820f-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="f820f-125">2.单击**引用**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f820f-125">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="f820f-126">3.单击**引用路径...**按钮。</span><span class="sxs-lookup"><span data-stu-id="f820f-126">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="f820f-127">4.在**引用路径**对话框框中，输入中的目录名称**文件夹︰**框。</span><span class="sxs-lookup"><span data-stu-id="f820f-127">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="f820f-128">5.单击**将文件夹添加**。</span><span class="sxs-lookup"><span data-stu-id="f820f-128">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f820f-129">示例</span><span class="sxs-lookup"><span data-stu-id="f820f-129">Example</span></span>  
 <span data-ttu-id="f820f-130">下面的代码编译`T2.vb`若要创建的.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="f820f-130">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="f820f-131">对于程序集引用，则编译器查找的工作目录中、 c︰ 驱动器的根目录中和 c︰ 驱动器的新的程序集目录中。</span><span class="sxs-lookup"><span data-stu-id="f820f-131">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f820f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f820f-132">See Also</span></span>  
 <span data-ttu-id="f820f-133">[程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="f820f-133">[Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="f820f-134"> [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f820f-134"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f820f-135"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="f820f-135"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
