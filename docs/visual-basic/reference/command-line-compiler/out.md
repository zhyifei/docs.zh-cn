---
title: /out (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d98a9f3cadc42021c302915cfc5b058b41e11ec6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="out-visual-basic"></a><span data-ttu-id="e5545-102">/out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5545-102">/out (Visual Basic)</span></span>
<span data-ttu-id="e5545-103">指定输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e5545-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5545-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5545-104">Syntax</span></span>  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="e5545-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5545-105">Arguments</span></span>  
  
|<span data-ttu-id="e5545-106">术语</span><span class="sxs-lookup"><span data-stu-id="e5545-106">Term</span></span>|<span data-ttu-id="e5545-107">定义</span><span class="sxs-lookup"><span data-stu-id="e5545-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="e5545-108">必需。</span><span class="sxs-lookup"><span data-stu-id="e5545-108">Required.</span></span> <span data-ttu-id="e5545-109">编译器创建输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e5545-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="e5545-110">如果文件名包含空格，则将名称括在双引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="e5545-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5545-111">备注</span><span class="sxs-lookup"><span data-stu-id="e5545-111">Remarks</span></span>  
 <span data-ttu-id="e5545-112">指定的完整名称和要创建的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="e5545-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="e5545-113">如果不这样做，.exe 文件将从源代码文件包含其名称`Sub Main`过程中和.dll 文件的第一个源代码文件采用其名称。</span><span class="sxs-lookup"><span data-stu-id="e5545-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="e5545-114">如果指定一个不带扩展名为.exe 或.dll 的文件名称，编译器会自动添加扩展，具体取决于指定的值`/target`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="e5545-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `/target` compiler option.</span></span>  
  
|<span data-ttu-id="e5545-115">若要在 Visual Studio 集成的开发环境中设置 /out</span><span class="sxs-lookup"><span data-stu-id="e5545-115">To set /out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e5545-116">1.在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="e5545-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e5545-117">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="e5545-117">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="e5545-118">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="e5545-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="e5545-119">2.单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="e5545-119">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="e5545-120">3.修改中的值**程序集名称**框。</span><span class="sxs-lookup"><span data-stu-id="e5545-120">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e5545-121">示例</span><span class="sxs-lookup"><span data-stu-id="e5545-121">Example</span></span>  
 <span data-ttu-id="e5545-122">下面的代码编译`T2.vb`并创建输出文件`T2.exe`。</span><span class="sxs-lookup"><span data-stu-id="e5545-122">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5545-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5545-123">See Also</span></span>  
 [<span data-ttu-id="e5545-124">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="e5545-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e5545-125">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5545-125">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="e5545-126">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="e5545-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
