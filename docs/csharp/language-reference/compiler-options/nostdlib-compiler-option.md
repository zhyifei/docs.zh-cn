---
title: "-nostdlib（C# 编译器选项）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nostdlib
dev_langs:
- CSharp
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1d500e2e55ab3117aa674e11d6cdd25703035879
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="nostdlib-c-compiler-options"></a><span data-ttu-id="e6b70-102">/nostdlib（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="e6b70-102">/nostdlib (C# Compiler Options)</span></span>
<span data-ttu-id="e6b70-103">**/nostdlib** 可防止导入 mscorlib.dll，这定义了整个 System 命名空间。</span><span class="sxs-lookup"><span data-stu-id="e6b70-103">**/nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6b70-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6b70-104">Syntax</span></span>  
  
```console  
/nostdlib[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="e6b70-105">备注</span><span class="sxs-lookup"><span data-stu-id="e6b70-105">Remarks</span></span>  
 <span data-ttu-id="e6b70-106">如果你想要定义或创建自己的 System 命名空间和对象，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="e6b70-106">Use this option if you want to define or create your own System namespace and objects.</span></span>  
  
 <span data-ttu-id="e6b70-107">如果未指定 **/nostdlib**，则 mscorlib.dll 将被导入到程序中（与指定 **/nostdlib-**相同）。</span><span class="sxs-lookup"><span data-stu-id="e6b70-107">If you do not specify **/nostdlib**, mscorlib.dll will be imported into your program (same as specifying **/nostdlib-**).</span></span> <span data-ttu-id="e6b70-108">指定 **/nostdlib** 与指定 **/nostdlib+**相同。</span><span class="sxs-lookup"><span data-stu-id="e6b70-108">Specifying **/nostdlib** is the same as specifying **/nostdlib+**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e6b70-109">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="e6b70-109">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="e6b70-110">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="e6b70-110">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="e6b70-111">单击“生成”  属性页。</span><span class="sxs-lookup"><span data-stu-id="e6b70-111">Click the **Build** properties page.</span></span>  
  
3.  <span data-ttu-id="e6b70-112">单击 **“高级”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e6b70-112">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="e6b70-113">修改“不引用 mscorlib.dll”  属性。</span><span class="sxs-lookup"><span data-stu-id="e6b70-113">Modify the **Do not reference mscorlib.dll** property.</span></span>  
  
 <span data-ttu-id="e6b70-114">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>。</span><span class="sxs-lookup"><span data-stu-id="e6b70-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b70-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6b70-115">See Also</span></span>  
 [<span data-ttu-id="e6b70-116">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="e6b70-116">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

