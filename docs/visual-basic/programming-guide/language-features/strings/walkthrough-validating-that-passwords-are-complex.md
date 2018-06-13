---
title: 验证密码复杂性 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: acfc8ab958c8671ed7f1afd245d24a43ca12be29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650278"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="c5310-102">演练：验证密码是否复杂 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5310-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="c5310-103">此方法检查某些强密码特征，并使用有关哪些检查密码失败的信息更新的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="c5310-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="c5310-104">密码可以在一个安全系统，用于授权的用户。</span><span class="sxs-lookup"><span data-stu-id="c5310-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="c5310-105">但是，密码必须是难以猜测未经授权的用户。</span><span class="sxs-lookup"><span data-stu-id="c5310-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="c5310-106">攻击者可以使用*字典攻击*程序，它循环访问的所有单词在字典 （或在不同语言中的多个字典） 并测试是否有任何单词就是用户的密码。</span><span class="sxs-lookup"><span data-stu-id="c5310-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="c5310-107">可以快速猜到弱的密码，例如"杨基棒球队"或"Mustang"。</span><span class="sxs-lookup"><span data-stu-id="c5310-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="c5310-108">强密码，如"？你L1N3vaFiNdMeyeP@sSWerd！"，大大降低可能会被猜到。</span><span class="sxs-lookup"><span data-stu-id="c5310-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="c5310-109">受密码保护的系统应确保用户选择强密码。</span><span class="sxs-lookup"><span data-stu-id="c5310-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="c5310-110">强密码很复杂 （包含大写、 小写、 数字和特殊字符的组合），不是一个单词。</span><span class="sxs-lookup"><span data-stu-id="c5310-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="c5310-111">此示例演示如何验证复杂性。</span><span class="sxs-lookup"><span data-stu-id="c5310-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5310-112">示例</span><span class="sxs-lookup"><span data-stu-id="c5310-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="c5310-113">代码</span><span class="sxs-lookup"><span data-stu-id="c5310-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c5310-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="c5310-114">Compiling the Code</span></span>  
 <span data-ttu-id="c5310-115">通过传递包含该密码的字符串调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c5310-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="c5310-116">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c5310-116">This example requires:</span></span>  
  
-   <span data-ttu-id="c5310-117">对 <xref:System.Text.RegularExpressions> 命名空间成员的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c5310-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="c5310-118">如果未在代码中完全限定成员名称，则添加 `Imports` 语句。</span><span class="sxs-lookup"><span data-stu-id="c5310-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="c5310-119">有关详细信息，请参阅 [Imports 语句（.NET 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。</span><span class="sxs-lookup"><span data-stu-id="c5310-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="c5310-120">安全性</span><span class="sxs-lookup"><span data-stu-id="c5310-120">Security</span></span>  
 <span data-ttu-id="c5310-121">如果在通过网络迁移密码，你需要使用安全的方法来传输数据。</span><span class="sxs-lookup"><span data-stu-id="c5310-121">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="c5310-122">有关详细信息，请参阅[ASP.NET Web 应用程序安全性](https://msdn.microsoft.com/library/330a99hc)。</span><span class="sxs-lookup"><span data-stu-id="c5310-122">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="c5310-123">你可以提高准确性`ValidatePassword`通过添加其他复杂性检查的函数：</span><span class="sxs-lookup"><span data-stu-id="c5310-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="c5310-124">密码和对用户的名称、 用户标识符和应用程序定义的字典及其子字符串进行比较。</span><span class="sxs-lookup"><span data-stu-id="c5310-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="c5310-125">在执行比较时此外，将看上去很相似字符视为等效项。</span><span class="sxs-lookup"><span data-stu-id="c5310-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="c5310-126">例如，将字母"l"和"e"视为等效于数字"1"和"3"。</span><span class="sxs-lookup"><span data-stu-id="c5310-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="c5310-127">如果只有一个大写字符，请确保它不是密码的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="c5310-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="c5310-128">请确保密码的最后两个字符的字母字符。</span><span class="sxs-lookup"><span data-stu-id="c5310-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="c5310-129">不允许从键盘的首行输入所有符号的密码。</span><span class="sxs-lookup"><span data-stu-id="c5310-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5310-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5310-130">See Also</span></span>  
 <xref:System.Text.RegularExpressions.Regex>  
 [<span data-ttu-id="c5310-131">ASP.NET Web 应用程序安全性</span><span class="sxs-lookup"><span data-stu-id="c5310-131">ASP.NET Web Application Security</span></span>](https://msdn.microsoft.com/library/330a99hc)
