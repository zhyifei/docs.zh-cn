---
title: "-preferreduilang（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4fcf075dd951d733d294a62de98365c77b16a51d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="63457-102">-preferreduilang（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="63457-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="63457-103">通过使用 `-preferreduilang` 编译器选项，可指定 C# 编译器显示输出的语言，如错误消息。</span><span class="sxs-lookup"><span data-stu-id="63457-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63457-104">语法</span><span class="sxs-lookup"><span data-stu-id="63457-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="63457-105">自变量</span><span class="sxs-lookup"><span data-stu-id="63457-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="63457-106">用于编译器输出的语言的[语言名称](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="63457-106">The [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63457-107">备注</span><span class="sxs-lookup"><span data-stu-id="63457-107">Remarks</span></span>  
 <span data-ttu-id="63457-108">可以使用 `-preferreduilang` 编译器选项指定 C# 编译器用于错误消息和其他命令行输出的语言。</span><span class="sxs-lookup"><span data-stu-id="63457-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="63457-109">如果未安装针对该语言的语言包，将改用操作系统的语言设置，而不会报告错误。</span><span class="sxs-lookup"><span data-stu-id="63457-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="63457-110">惠?</span><span class="sxs-lookup"><span data-stu-id="63457-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63457-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="63457-111">See Also</span></span>  
 [<span data-ttu-id="63457-112">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="63457-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
