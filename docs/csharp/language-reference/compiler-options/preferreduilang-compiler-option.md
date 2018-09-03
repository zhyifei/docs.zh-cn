---
title: -preferreduilang（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: a1fbbb8415e5e3405f039489aa071b0624065a9d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405886"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="04651-102">-preferreduilang（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="04651-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="04651-103">通过使用 `-preferreduilang` 编译器选项，可指定 C# 编译器显示输出的语言，如错误消息。</span><span class="sxs-lookup"><span data-stu-id="04651-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04651-104">语法</span><span class="sxs-lookup"><span data-stu-id="04651-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="04651-105">自变量</span><span class="sxs-lookup"><span data-stu-id="04651-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="04651-106">用于编译器输出的语言的[语言名称](/windows/desktop/Intl/language-names)。</span><span class="sxs-lookup"><span data-stu-id="04651-106">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04651-107">备注</span><span class="sxs-lookup"><span data-stu-id="04651-107">Remarks</span></span>  
 <span data-ttu-id="04651-108">可以使用 `-preferreduilang` 编译器选项指定 C# 编译器用于错误消息和其他命令行输出的语言。</span><span class="sxs-lookup"><span data-stu-id="04651-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="04651-109">如果未安装针对该语言的语言包，将改用操作系统的语言设置，而不会报告错误。</span><span class="sxs-lookup"><span data-stu-id="04651-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="04651-110">要求</span><span class="sxs-lookup"><span data-stu-id="04651-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04651-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="04651-111">See Also</span></span>

- [<span data-ttu-id="04651-112">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="04651-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
