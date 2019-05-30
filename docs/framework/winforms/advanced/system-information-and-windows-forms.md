---
title: 系统信息和 Windows 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: 2edc2e867259f8884467c3d5b0ae3d22ba391a77
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380108"
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="13f04-102">系统信息和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="13f04-102">System Information and Windows Forms</span></span>
<span data-ttu-id="13f04-103">有时有必要收集有关你的应用程序运行才能在你的代码中进行决策的计算机的信息。</span><span class="sxs-lookup"><span data-stu-id="13f04-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="13f04-104">例如，可能有一个函数，则仅当连接到特定网络域; 适用在这种情况下需要一种方法来确定域并禁用函数，如果域不存在。</span><span class="sxs-lookup"><span data-stu-id="13f04-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="13f04-105">Windows 窗体应用程序可以使用<xref:System.Windows.Forms.SystemInformation>类来确定在运行时执行大量有关计算机的操作。</span><span class="sxs-lookup"><span data-stu-id="13f04-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="13f04-106">下面的示例演示了如何使用<xref:System.Windows.Forms.SystemInformation>类来检索<xref:System.Windows.Forms.SystemInformation.UserName%2A>和<xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span><span class="sxs-lookup"><span data-stu-id="13f04-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to "
+ Domain);
```  
  
 <span data-ttu-id="13f04-107">所有成员<xref:System.Windows.Forms.SystemInformation>类是只读的不能修改用户的设置。</span><span class="sxs-lookup"><span data-stu-id="13f04-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="13f04-108">有 100 多个类的成员，从监视器连接到计算机的数目上的所有内容返回信息 (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) 到 Windows 资源管理器中的图标的间距 (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A>和<xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>)。</span><span class="sxs-lookup"><span data-stu-id="13f04-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="13f04-109">一些更有用的成员<xref:System.Windows.Forms.SystemInformation>类包含<xref:System.Windows.Forms.SystemInformation.ComputerName%2A>， <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>， <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>，和<xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>。</span><span class="sxs-lookup"><span data-stu-id="13f04-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f04-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="13f04-110">See also</span></span>

- <xref:System.Windows.Forms.SystemInformation>
- [<span data-ttu-id="13f04-111">Windows 窗体中的电源管理</span><span class="sxs-lookup"><span data-stu-id="13f04-111">Power Management in Windows Forms</span></span>](power-management-in-windows-forms.md)
