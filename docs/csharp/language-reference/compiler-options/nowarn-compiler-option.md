---
title: -nowarn（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /nowarn
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
ms.openlocfilehash: 76bb008c40d84ed6048b8f960f050048319273b9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43421923"
---
# <a name="-nowarn-c-compiler-options"></a><span data-ttu-id="966c3-102">-nowarn（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="966c3-102">-nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="966c3-103">使用 -nowarn 选项可以禁止编译器显示一个或多个警告。</span><span class="sxs-lookup"><span data-stu-id="966c3-103">The **-nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="966c3-104">使用逗号分隔多个警告编号。</span><span class="sxs-lookup"><span data-stu-id="966c3-104">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="966c3-105">语法</span><span class="sxs-lookup"><span data-stu-id="966c3-105">Syntax</span></span>  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="966c3-106">自变量</span><span class="sxs-lookup"><span data-stu-id="966c3-106">Arguments</span></span>  
 <span data-ttu-id="966c3-107">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="966c3-107">`number1`, `number2`</span></span>  
 <span data-ttu-id="966c3-108">希望编译器禁止显示的警告编号。</span><span class="sxs-lookup"><span data-stu-id="966c3-108">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="966c3-109">备注</span><span class="sxs-lookup"><span data-stu-id="966c3-109">Remarks</span></span>  
 <span data-ttu-id="966c3-110">只应指定警告标识符的数值部分。</span><span class="sxs-lookup"><span data-stu-id="966c3-110">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="966c3-111">例如，如果要禁止显示 CS0028，则可以指定 `-nowarn:28`。</span><span class="sxs-lookup"><span data-stu-id="966c3-111">For example, if you want to suppress CS0028, you could specify `-nowarn:28`.</span></span>  
  
 <span data-ttu-id="966c3-112">编译器会以无提示方式忽略传递给 `-nowarn` 的警告编号，这些编号在早期版本中有效，但已从编译器中移除。</span><span class="sxs-lookup"><span data-stu-id="966c3-112">The compiler will silently ignore warning numbers passed to `-nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="966c3-113">例如，CS0679 在 Visual Studio .NET 2002 的编译器中有效，但是在后来已移除。</span><span class="sxs-lookup"><span data-stu-id="966c3-113">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="966c3-114">无法通过 `-nowarn` 选项禁止显示以下警告：</span><span class="sxs-lookup"><span data-stu-id="966c3-114">The following warnings cannot be suppressed by the `-nowarn` option:</span></span>  
  
-   <span data-ttu-id="966c3-115">编译器警告（等级 1）CS2002</span><span class="sxs-lookup"><span data-stu-id="966c3-115">Compiler Warning (level 1) CS2002</span></span>  
  
-   <span data-ttu-id="966c3-116">编译器警告（等级 1）CS2023</span><span class="sxs-lookup"><span data-stu-id="966c3-116">Compiler Warning (level 1) CS2023</span></span>  
  
-   <span data-ttu-id="966c3-117">编译器警告（等级 1）CS2029</span><span class="sxs-lookup"><span data-stu-id="966c3-117">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="966c3-118">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="966c3-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="966c3-119">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="966c3-119">Open the **Properties** page for the project.</span></span> <span data-ttu-id="966c3-120">有关详细信息，请参阅[“项目设计器”->“生成”页 (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)。</span><span class="sxs-lookup"><span data-stu-id="966c3-120">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="966c3-121">单击“生成”属性页。</span><span class="sxs-lookup"><span data-stu-id="966c3-121">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="966c3-122">修改“禁止显示警告”属性。</span><span class="sxs-lookup"><span data-stu-id="966c3-122">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="966c3-123">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>。</span><span class="sxs-lookup"><span data-stu-id="966c3-123">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="966c3-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="966c3-124">See Also</span></span>  

- [<span data-ttu-id="966c3-125">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="966c3-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="966c3-126">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="966c3-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
- [<span data-ttu-id="966c3-127">C# 编译器错误</span><span class="sxs-lookup"><span data-stu-id="966c3-127">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
