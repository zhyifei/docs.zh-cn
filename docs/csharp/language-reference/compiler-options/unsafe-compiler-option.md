---
title: "-unsafe（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.assetid: fdb77ed9-da03-45bd-bb7f-250704da1bcc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b253a9ddafead823480f9893e809f17b6c22a179
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="1568f-102">-unsafe（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="1568f-102">-unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="1568f-103">-unsafe 编译器选项允许使用[不安全](../../../csharp/language-reference/keywords/unsafe.md)关键字进行编译的代码。</span><span class="sxs-lookup"><span data-stu-id="1568f-103">The **-unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1568f-104">语法</span><span class="sxs-lookup"><span data-stu-id="1568f-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="1568f-105">备注</span><span class="sxs-lookup"><span data-stu-id="1568f-105">Remarks</span></span>  
 <span data-ttu-id="1568f-106">有关不安全代码的详细信息，请参阅[不安全代码和指针](../../../csharp/programming-guide/unsafe-code-pointers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1568f-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="1568f-107">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="1568f-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="1568f-108">打开项目的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="1568f-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="1568f-109">单击“生成”属性页。</span><span class="sxs-lookup"><span data-stu-id="1568f-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="1568f-110">选中“允许不安全代码”复选框。</span><span class="sxs-lookup"><span data-stu-id="1568f-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
 <span data-ttu-id="1568f-111">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>。</span><span class="sxs-lookup"><span data-stu-id="1568f-111">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1568f-112">示例</span><span class="sxs-lookup"><span data-stu-id="1568f-112">Example</span></span>  
 <span data-ttu-id="1568f-113">针对不安全模式编译 `in.cs`：</span><span class="sxs-lookup"><span data-stu-id="1568f-113">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="1568f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1568f-114">See Also</span></span>  
 [<span data-ttu-id="1568f-115">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="1568f-115">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="1568f-116">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="1568f-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
