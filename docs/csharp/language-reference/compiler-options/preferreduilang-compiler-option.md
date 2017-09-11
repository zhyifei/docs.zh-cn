---
title: "-preferreduilang（C# 编译器选项）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /preferreduilang
dev_langs:
- CSharp
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b94c2794642ad93a78eaafdeb655310e4ecb2d25
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="preferreduilang-c-compiler-options"></a><span data-ttu-id="1f631-102">/preferreduilang（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="1f631-102">/preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="1f631-103">通过使用 `/preferreduilang` 编译器选项，可指定 C# 编译器显示输出的语言，如错误消息。</span><span class="sxs-lookup"><span data-stu-id="1f631-103">By using the `/preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f631-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f631-104">Syntax</span></span>  
  
```console  
/preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="1f631-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f631-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="1f631-106">用于编译器输出的语言的[语言名称](http://go.microsoft.com/fwlink/p/?LinkId=236992)。</span><span class="sxs-lookup"><span data-stu-id="1f631-106">The [language name](http://go.microsoft.com/fwlink/p/?LinkId=236992) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f631-107">备注</span><span class="sxs-lookup"><span data-stu-id="1f631-107">Remarks</span></span>  
 <span data-ttu-id="1f631-108">可以使用 `/preferreduilang` 编译器选项指定 C# 编译器用于错误消息和其他命令行输出的语言。</span><span class="sxs-lookup"><span data-stu-id="1f631-108">You can use the `/preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="1f631-109">如果未安装针对该语言的语言包，将改用操作系统的语言设置，而不会报告错误。</span><span class="sxs-lookup"><span data-stu-id="1f631-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe /preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="1f631-110">要求</span><span class="sxs-lookup"><span data-stu-id="1f631-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f631-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f631-111">See Also</span></span>  
 [<span data-ttu-id="1f631-112">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="1f631-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

