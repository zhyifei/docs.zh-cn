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
ms.openlocfilehash: 7ebafcf446c9033c93e0c5fa5e11ea2930bd2e1e
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602555"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="5a6a3-102">-preferreduilang（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="5a6a3-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="5a6a3-103">通过使用 `-preferreduilang` 编译器选项，可指定 C# 编译器显示输出的语言，如错误消息。</span><span class="sxs-lookup"><span data-stu-id="5a6a3-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a6a3-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a6a3-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="5a6a3-105">自变量</span><span class="sxs-lookup"><span data-stu-id="5a6a3-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="5a6a3-106">用于编译器输出的语言的[语言名称](/windows/desktop/Intl/language-names)。</span><span class="sxs-lookup"><span data-stu-id="5a6a3-106">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a6a3-107">备注</span><span class="sxs-lookup"><span data-stu-id="5a6a3-107">Remarks</span></span>  
 <span data-ttu-id="5a6a3-108">可以使用 `-preferreduilang` 编译器选项指定 C# 编译器用于错误消息和其他命令行输出的语言。</span><span class="sxs-lookup"><span data-stu-id="5a6a3-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="5a6a3-109">如果未安装针对该语言的语言包，将改用操作系统的语言设置，而不会报告错误。</span><span class="sxs-lookup"><span data-stu-id="5a6a3-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="5a6a3-110">要求</span><span class="sxs-lookup"><span data-stu-id="5a6a3-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a6a3-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a6a3-111">See also</span></span>

- [<span data-ttu-id="5a6a3-112">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="5a6a3-112">C# Compiler Options</span></span>](./index.md)
