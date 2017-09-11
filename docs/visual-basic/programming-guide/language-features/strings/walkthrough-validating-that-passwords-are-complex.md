---
title: "验证密码复杂性 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- String data type, validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8d636c1e43de6a108cdc217cb21aaf7689e175f7
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="00938-102">演练：验证密码是否复杂 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00938-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="00938-103">此方法检查某些强密码特征，并使用哪些检查密码失败的信息更新的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="00938-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="00938-104">密码可以在一个安全的系统，用于对用户授权。</span><span class="sxs-lookup"><span data-stu-id="00938-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="00938-105">但是，密码必须是未经授权的用户猜测困难。</span><span class="sxs-lookup"><span data-stu-id="00938-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="00938-106">攻击者可以使用*字典攻击*的程序，该循环访问所有字典 （或多个不同的语言字典） 中的单词，并测试是否有任何单词就是用户的密码。</span><span class="sxs-lookup"><span data-stu-id="00938-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="00938-107">例如，"杨基棒球队"或"Mustang"弱密码可以快速猜到。</span><span class="sxs-lookup"><span data-stu-id="00938-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="00938-108">更强的密码，如"？您L1N3vaFiNdMeyeP@sSWerd！"，也更不容易被猜到。</span><span class="sxs-lookup"><span data-stu-id="00938-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="00938-109">受密码保护的系统应确保用户选择强密码。</span><span class="sxs-lookup"><span data-stu-id="00938-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="00938-110">强密码很复杂 （包含大写、 小写字母、 数字和特殊字符的组合），不是一个单词。</span><span class="sxs-lookup"><span data-stu-id="00938-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="00938-111">此示例演示如何验证复杂性。</span><span class="sxs-lookup"><span data-stu-id="00938-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00938-112">示例</span><span class="sxs-lookup"><span data-stu-id="00938-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="00938-113">代码</span><span class="sxs-lookup"><span data-stu-id="00938-113">Code</span></span>  
 <span data-ttu-id="00938-114">[!code-vb[VbVbcnRegEx #&1;](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="00938-114">[!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00938-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="00938-115">Compiling the Code</span></span>  
 <span data-ttu-id="00938-116">调用此方法通过传递包含该密码的字符串。</span><span class="sxs-lookup"><span data-stu-id="00938-116">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="00938-117">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="00938-117">This example requires:</span></span>  
  
-   <span data-ttu-id="00938-118">对成员的访问<xref:System.Text.RegularExpressions>命名空间。</xref:System.Text.RegularExpressions></span><span class="sxs-lookup"><span data-stu-id="00938-118">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="00938-119">添加`Imports`如果在代码中的成员名称不完全限定，您需要的语句。</span><span class="sxs-lookup"><span data-stu-id="00938-119">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="00938-120">有关详细信息，请参阅 [Imports 语句（.NET 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。</span><span class="sxs-lookup"><span data-stu-id="00938-120">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="00938-121">安全性</span><span class="sxs-lookup"><span data-stu-id="00938-121">Security</span></span>  
 <span data-ttu-id="00938-122">如果在通过网络迁移密码，您需要使用安全的方法来传输数据。</span><span class="sxs-lookup"><span data-stu-id="00938-122">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="00938-123">有关详细信息，请参阅[ASP.NET Web 应用程序安全性](https://msdn.microsoft.com/library/330a99hc)。</span><span class="sxs-lookup"><span data-stu-id="00938-123">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="00938-124">您可以提高准确性`ValidatePassword`通过添加额外的复杂性检查函数︰</span><span class="sxs-lookup"><span data-stu-id="00938-124">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="00938-125">将密码和针对用户的名称、 用户标识符和应用程序定义的字典及其子字符串进行比较。</span><span class="sxs-lookup"><span data-stu-id="00938-125">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="00938-126">在执行比较此外，将看上去很相似字符视为等效。</span><span class="sxs-lookup"><span data-stu-id="00938-126">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="00938-127">例如，将字母"l"和"e"视为等效于数字"1"和"3"。</span><span class="sxs-lookup"><span data-stu-id="00938-127">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="00938-128">如果只有一个大写字符，请确保它不是第一个字符的密码。</span><span class="sxs-lookup"><span data-stu-id="00938-128">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="00938-129">请确保密码的最后两个字符的字母字符。</span><span class="sxs-lookup"><span data-stu-id="00938-129">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="00938-130">不允许从键盘上的首行输入所有符号的密码。</span><span class="sxs-lookup"><span data-stu-id="00938-130">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00938-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00938-131">See Also</span></span>  
 <span data-ttu-id="00938-132"><xref:System.Text.RegularExpressions.Regex></xref:System.Text.RegularExpressions.Regex></span><span class="sxs-lookup"><span data-stu-id="00938-132"><xref:System.Text.RegularExpressions.Regex></span></span>   
<span data-ttu-id="00938-133"> [ASP.NET Web 应用程序安全性](https://msdn.microsoft.com/library/330a99hc)</span><span class="sxs-lookup"><span data-stu-id="00938-133"> [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc)</span></span>
