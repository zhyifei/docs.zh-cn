---
title: 保护状态数据
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c821177ca897e617885425217ac0b6659b5ea6e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44212225"
---
# <a name="securing-state-data"></a><span data-ttu-id="a9fff-102">保护状态数据</span><span class="sxs-lookup"><span data-stu-id="a9fff-102">Securing State Data</span></span>
<span data-ttu-id="a9fff-103">处理敏感数据或做出任何种类的安全决策的应用程序需要将相关数据保持在自己的控制之下，而不允许其他可能的恶意代码直接访问这些数据。</span><span class="sxs-lookup"><span data-stu-id="a9fff-103">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="a9fff-104">保护内存中的数据的最好方法就是，将数据声明为私有或内部（范围限定为相同的程序集内）变量。</span><span class="sxs-lookup"><span data-stu-id="a9fff-104">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="a9fff-105">然而，即使这些数据受到访问权制约，你也应当注意：</span><span class="sxs-lookup"><span data-stu-id="a9fff-105">However, even this data is subject to access you should be aware of:</span></span>  
  
-   <span data-ttu-id="a9fff-106">通过使用反射机制，那些能够引用你的对象的、高度受信任的代码可以获取和设置私有成员。</span><span class="sxs-lookup"><span data-stu-id="a9fff-106">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
-   <span data-ttu-id="a9fff-107">使用序列化时，如果高度受信任的代码可以访问序列化形式的对象中的相应数据，那么它就可以有效地获取和设置私有成员。</span><span class="sxs-lookup"><span data-stu-id="a9fff-107">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
-   <span data-ttu-id="a9fff-108">调试时，可以读取这些数据。</span><span class="sxs-lookup"><span data-stu-id="a9fff-108">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="a9fff-109">千万不要让你自己的任何方法或属性在无意中公开这些值。</span><span class="sxs-lookup"><span data-stu-id="a9fff-109">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fff-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9fff-110">See also</span></span>

- [<span data-ttu-id="a9fff-111">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="a9fff-111">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
