---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 380e71e462f736d4564a37b83567007fa9461b05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332958"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="664ca-102">-imports （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="664ca-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="664ca-103">从指定的程序集导入命名空间。</span><span class="sxs-lookup"><span data-stu-id="664ca-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="664ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="664ca-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="664ca-105">参数</span><span class="sxs-lookup"><span data-stu-id="664ca-105">Arguments</span></span>  
  
|<span data-ttu-id="664ca-106">术语</span><span class="sxs-lookup"><span data-stu-id="664ca-106">Term</span></span>|<span data-ttu-id="664ca-107">Definition</span><span class="sxs-lookup"><span data-stu-id="664ca-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="664ca-108">必需。</span><span class="sxs-lookup"><span data-stu-id="664ca-108">Required.</span></span> <span data-ttu-id="664ca-109">要导入的命名空间的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="664ca-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="664ca-110">备注</span><span class="sxs-lookup"><span data-stu-id="664ca-110">Remarks</span></span>  
 <span data-ttu-id="664ca-111">`-imports` 选项将导入在当前源文件集中或从任何引用的程序集内定义的任何命名空间。</span><span class="sxs-lookup"><span data-stu-id="664ca-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="664ca-112">使用 `-imports` 指定的命名空间中的成员可用于编译中的所有源代码文件。</span><span class="sxs-lookup"><span data-stu-id="664ca-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="664ca-113">使用[Imports 语句（.Net 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)可在单个源代码文件中使用命名空间。</span><span class="sxs-lookup"><span data-stu-id="664ca-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="664ca-114">在 Visual Studio 集成开发环境中设置/imports</span><span class="sxs-lookup"><span data-stu-id="664ca-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="664ca-115">1. 在**解决方案资源管理器**中选择了一个项目。</span><span class="sxs-lookup"><span data-stu-id="664ca-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="664ca-116">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="664ca-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="664ca-117">2. 单击 "**引用**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="664ca-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="664ca-118">3. 在 "**添加用户导入**" 按钮旁的框中输入命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="664ca-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="664ca-119">4. 单击 "**添加用户导入**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="664ca-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="664ca-120">示例</span><span class="sxs-lookup"><span data-stu-id="664ca-120">Example</span></span>  
 <span data-ttu-id="664ca-121">指定 `/imports:system.globalization` 时，将编译下面的代码。</span><span class="sxs-lookup"><span data-stu-id="664ca-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="664ca-122">如果没有此方法，则成功编译需要将 `Imports System.Globalization` 语句包含在源代码文件的开头，或者属性完全限定为 `System.Globalization.CultureInfo.CurrentCulture.Name`。</span><span class="sxs-lookup"><span data-stu-id="664ca-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="664ca-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="664ca-123">See also</span></span>

- [<span data-ttu-id="664ca-124">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="664ca-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="664ca-125">引用和 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="664ca-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="664ca-126">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="664ca-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
