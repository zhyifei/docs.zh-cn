---
title: "/win32icon |Microsoft 文档"
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
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: 13
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
ms.openlocfilehash: f7d451026438be722d6cb7eecfffe397ccff82ae
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="win32icon"></a><span data-ttu-id="face2-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="face2-102">/win32icon</span></span>
<span data-ttu-id="face2-103">在输出文件中插入.ico 文件。</span><span class="sxs-lookup"><span data-stu-id="face2-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="face2-104">此.ico 文件表示该输出文件**文件资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="face2-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="face2-105">语法</span><span class="sxs-lookup"><span data-stu-id="face2-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="face2-106">参数</span><span class="sxs-lookup"><span data-stu-id="face2-106">Arguments</span></span>  
  
|<span data-ttu-id="face2-107">术语</span><span class="sxs-lookup"><span data-stu-id="face2-107">Term</span></span>|<span data-ttu-id="face2-108">定义</span><span class="sxs-lookup"><span data-stu-id="face2-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="face2-109">要添加到输出文件的.ico 文件。</span><span class="sxs-lookup"><span data-stu-id="face2-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="face2-110">将文件名括在双引号 ("") 如果包含空格。</span><span class="sxs-lookup"><span data-stu-id="face2-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="face2-111">备注</span><span class="sxs-lookup"><span data-stu-id="face2-111">Remarks</span></span>  
 <span data-ttu-id="face2-112">您可以使用 Microsoft Windows 资源编译器 (RC) 创建.ico 文件。</span><span class="sxs-lookup"><span data-stu-id="face2-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="face2-113">资源编译器当编译 Visual c + + 程序;.ico 文件创建从.rc 文件中。</span><span class="sxs-lookup"><span data-stu-id="face2-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="face2-114">`/win32icon`和`/win32resource`是互相排斥的选项。</span><span class="sxs-lookup"><span data-stu-id="face2-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="face2-115">请参阅[/linkresource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/linkresource.md)引用[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]资源文件或[/resource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/resource.md)附加[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]资源文件。</span><span class="sxs-lookup"><span data-stu-id="face2-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file.</span></span> <span data-ttu-id="face2-116">请参阅[/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) .res 文件导入。</span><span class="sxs-lookup"><span data-stu-id="face2-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="face2-117">在 Visual Studio IDE 中设置 /win32icon</span><span class="sxs-lookup"><span data-stu-id="face2-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="face2-118">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="face2-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="face2-119">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="face2-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="face2-120">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="face2-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="face2-121">2.单击“应用程序” **** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="face2-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="face2-122">3.在修改此值**图标**框。</span><span class="sxs-lookup"><span data-stu-id="face2-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="face2-123">示例</span><span class="sxs-lookup"><span data-stu-id="face2-123">Example</span></span>  
 <span data-ttu-id="face2-124">下面的代码编译`In.vb`并附加一个.ico 文件、 `Rf.ico`。</span><span class="sxs-lookup"><span data-stu-id="face2-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="face2-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="face2-125">See Also</span></span>  
 <span data-ttu-id="face2-126">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="face2-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="face2-127"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="face2-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
