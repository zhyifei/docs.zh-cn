---
title: "-nostdlib（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dd9d2b6a4a9c774aa339e840ad0020ee39cb10d3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="446b3-102">-nostdlib（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="446b3-102">-nostdlib (C# Compiler Options)</span></span>
<span data-ttu-id="446b3-103">-nostdlib 可防止导入 mscorlib.dll，后者定义了整个 System 命名空间。</span><span class="sxs-lookup"><span data-stu-id="446b3-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="446b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="446b3-104">Syntax</span></span>  
  
```console  
-nostdlib[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="446b3-105">备注</span><span class="sxs-lookup"><span data-stu-id="446b3-105">Remarks</span></span>  
 <span data-ttu-id="446b3-106">如果你想要定义或创建自己的 System 命名空间和对象，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="446b3-106">Use this option if you want to define or create your own System namespace and objects.</span></span>  
  
 <span data-ttu-id="446b3-107">如果未指定 -nostdlib，则 mscorlib.dll 将被导入到程序中（与指定 -nostdlib- 相同）。</span><span class="sxs-lookup"><span data-stu-id="446b3-107">If you do not specify **-nostdlib**, mscorlib.dll will be imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="446b3-108">指定 -nostdlib 与指定 -nostdlib+ 相同。</span><span class="sxs-lookup"><span data-stu-id="446b3-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="446b3-109">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="446b3-109">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="446b3-110">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="446b3-110">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="446b3-111">单击“生成”  属性页。</span><span class="sxs-lookup"><span data-stu-id="446b3-111">Click the **Build** properties page.</span></span>  
  
3.  <span data-ttu-id="446b3-112">单击 **“高级”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="446b3-112">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="446b3-113">修改“不引用 mscorlib.dll”  属性。</span><span class="sxs-lookup"><span data-stu-id="446b3-113">Modify the **Do not reference mscorlib.dll** property.</span></span>  
  
 <span data-ttu-id="446b3-114">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>。</span><span class="sxs-lookup"><span data-stu-id="446b3-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="446b3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="446b3-115">See Also</span></span>  
 [<span data-ttu-id="446b3-116">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="446b3-116">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
