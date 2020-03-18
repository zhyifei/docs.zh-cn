---
title: -codepage（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 3352e7fc446ace391540360a3b6b36d604ca5f13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173752"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="e4786-102">-codepage（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="e4786-102">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="e4786-103">如果所需页不是系统的当前默认代码页，则此选项指定编译期间要使用的代码页。</span><span class="sxs-lookup"><span data-stu-id="e4786-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4786-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4786-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="e4786-105">参数</span><span class="sxs-lookup"><span data-stu-id="e4786-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="e4786-106">要用于编译中所有源代码文件的代码页 ID。</span><span class="sxs-lookup"><span data-stu-id="e4786-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4786-107">备注</span><span class="sxs-lookup"><span data-stu-id="e4786-107">Remarks</span></span>  
 <span data-ttu-id="e4786-108">编译器将首先尝试将所有源文件解释为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="e4786-108">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="e4786-109">如果源代码文件使用除 UTF-8 以外的编码并使用除 7 位 ASCII 字符以外的字符，请使用 -codepage 选项指定应使用的代码页  。</span><span class="sxs-lookup"><span data-stu-id="e4786-109">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="e4786-110">-codepage 适用于编译中的所有源代码文件  。</span><span class="sxs-lookup"><span data-stu-id="e4786-110">**-codepage** applies to all source code files in your compilation.</span></span>  

 <span data-ttu-id="e4786-111">有关如何查找系统上支持哪些代码页的信息，请参阅 [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo)。</span><span class="sxs-lookup"><span data-stu-id="e4786-111">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="e4786-112">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="e4786-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4786-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4786-113">See also</span></span>

- [<span data-ttu-id="e4786-114">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="e4786-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e4786-115">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="e4786-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
