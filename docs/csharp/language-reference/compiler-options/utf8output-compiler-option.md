---
title: "-utf8output（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /utf8output
helpviewer_keywords:
- utf8output compiler option [C#]
- /utf8output compiler option [C#]
- -utf8output compiler option [C#]
ms.assetid: 27ff7381-c281-45d7-b2eb-1ad644b1354e
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 95630afcfcd2ae9ab64660eb0f022dd0733b4c4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="utf8output-c-compiler-options"></a><span data-ttu-id="4c0b1-102">/utf8output（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="4c0b1-102">/utf8output (C# Compiler Options)</span></span>
<span data-ttu-id="4c0b1-103">/utf8output 选项使用 UTF-8 编码来显示编译器输出。</span><span class="sxs-lookup"><span data-stu-id="4c0b1-103">The **/utf8output** option displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c0b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="4c0b1-104">Syntax</span></span>  
  
```console  
/utf8output  
```  
  
## <a name="remarks"></a><span data-ttu-id="4c0b1-105">备注</span><span class="sxs-lookup"><span data-stu-id="4c0b1-105">Remarks</span></span>  
 <span data-ttu-id="4c0b1-106">在某些国际配置中，编译器输出无法在控制台上正确显示。</span><span class="sxs-lookup"><span data-stu-id="4c0b1-106">In some international configurations, compiler output cannot correctly be displayed in the console.</span></span> <span data-ttu-id="4c0b1-107">在这些配置中，请使用 /utf8output 并将编译器输出重定向到文件。</span><span class="sxs-lookup"><span data-stu-id="4c0b1-107">In these configurations, use **/utf8output** and redirect compiler output to a file.</span></span>  
  
 <span data-ttu-id="4c0b1-108">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="4c0b1-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c0b1-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c0b1-109">See Also</span></span>  
 [<span data-ttu-id="4c0b1-110">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="4c0b1-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
