---
title: 保证客户端应用程序的安全
ms.date: 03/30/2017
ms.assetid: 6239592e-fa7d-4dea-9f00-d296d0048b01
ms.openlocfilehash: a3b035d59a39ca20f6a81fbd40d39069a7cc43c2
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46529018"
---
# <a name="secure-client-applications"></a>保证客户端应用程序的安全
应用程序通常由多个部件组成，所有这些部件均不能包含漏洞，否则可能导致数据丢失或以其他方式危害系统。 在攻击者可访问数据或系统资源之前将其阻止，以此可创建安全的用户界面来防止出现许多问题。  
  
## <a name="validate-user-input"></a>验证用户输入  
 在构建访问数据的应用程序时，除非能够证明其不为恶意输入，否则您应该假定所有用户输入均为恶意输入。 如果未能实现此目的，则可能会使您的应用程序易于受到攻击。 .NET Framework 包含的类可帮助您约束输入控件的值的域，如限制可输入字符的数目。 使用事件挂钩，您可以编写用于检查值的有效性的程序。 可验证和强类型化用户输入数据，从而限制应用程序对脚本和 SQL 注入攻击的公开程度。  
  
> [!IMPORTANT]
>  您还必须验证数据源和客户端应用程序中的用户输入。 因为攻击者可能选择避开应用程序，而直接攻击数据源。  
  
 [安全性和用户输入](../../../../docs/standard/security/security-and-user-input.md)  
 描述如何处理与用户输入相关的细微和潜在危险缺陷。  
  
 [在 ASP.NET Web Pages 中验证用户输入](https://msdn.microsoft.com/library/4ad3dacb-89e0-4cee-89ac-40a3f2a85461)  
 概述如何使用 ASP.NET 验证控件验证用户输入。  
  
 [Windows 窗体中的用户输入](../../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 提供用于验证 Windows 窗体应用程序中鼠标和键盘输入的链接和信息。  
  
 [.NET Framework 正则表达式](../../../../docs/standard/base-types/regular-expressions.md)  
 描述如何使用 <xref:System.Text.RegularExpressions.Regex> 类检查用户输入的有效性。  
  
## <a name="windows-applications"></a>Windows 应用程序  
 过去，Windows 应用程序通常使用完全权限运行。 通过使用代码启用安全性 (CAS)，.NET Framework 可提供限制在 Windows 应用程序中执行代码的基础结构。 但是，仅使用 CAS 是不足以保护应用程序的。  
  
 [Windows 窗体安全](../../../../docs/framework/winforms/windows-forms-security.md)  
 讨论如何保证 Windows 窗体应用程序的安全并提供相关主题的链接。  
  
 [Windows 窗体和非托管应用程序](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)  
 描述如何与 Windows 窗体应用程序中的非托管应用程序进行交互。  
  
 [ClickOnce 部署的 Windows 窗体应用程序](https://msdn.microsoft.com/library/34d8c770-48f2-460c-8d67-4ea5684511df)  
 描述如何在 Windows 窗体应用程序中使用 `ClickOnce` 部署，并讨论安全含义。  
  
## <a name="aspnet-and-xml-web-services"></a>ASP.NET 和 XML Web services  
 ASP.NET 应用程序通常需要限制对 Web 站点某些部分的访问，并提供其他数据保护机制和站点安全机制。 这些链接可提供用于保护 ASP.NET 应用程序的有用信息。  
  
 XML Web services 能够提供可由 ASP.NET 应用程序、Windows 窗体应用程序或其他 Web 服务使用的数据。 您需要管理 Web 服务自身的安全性以及客户端应用程序的安全性。  
  
 有关更多信息，请参见以下资源。  
  
|资源|描述|  
|--------------|-----------------|  
|[NIB: ASP.NET 的安全性](https://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d)|讨论如何保证 ASP.NET 应用程序的安全。|  
|[保护使用 ASP.NET 创建的 XML Web Services](https://msdn.microsoft.com/library/354b2ab1-2782-4542-b32a-dc560178b90c)|讨论如何实现 ASP.NET Web 服务的安全性。|  
|[脚本侵入概述](https://msdn.microsoft.com/library/772c7312-211a-4eb3-8d6e-eec0aa1dcc07)|讨论如何抵御脚本攻击，该攻击会尝试将恶意字符插入网页。|  
|[NIB： 基本的 ASP.NET Web 应用程序的安全方案](https://msdn.microsoft.com/library/94a52ab8-731d-417e-b997-721baf43df38)|常规安全信息和指向更多讨论的链接，|  
  
## <a name="remoting"></a>远程处理  
 利用 .NET 远程处理，可以方便地生成广泛分布的应用程序，而不论应用程序组件是全部集中在一台计算机上，还是分布在世界各地。 生成的客户端应用程序可以使用同一台计算机（或可通过其网络连接到的任何其他计算机）上其他进程中的对象。 您还可以在同一进程中使用 .NET 远程处理与其他应用程序域进行通信。  
  
|资源|描述|  
|--------------|-----------------|  
|[远程应用程序的配置](https://msdn.microsoft.com/library/92c0c097-d984-4315-835b-7490ecdf1097)|讨论如何配置远程处理应用程序以避免出现常见问题。|  
|[远程处理中的安全性](https://msdn.microsoft.com/library/9574262c-d4b1-41c5-8600-24ff147c0add)|描述身份验证和加密以及与远程处理相关的其他安全主题。|  
|[安全性和远程处理注意事项](../../../../docs/framework/misc/security-and-remoting-considerations.md)|描述与受保护对象和应用程序域交叉相关的安全问题。|  
  
## <a name="see-also"></a>请参阅  
 [保证 ADO.NET 应用程序的安全](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [有关数据访问策略建议](https://msdn.microsoft.com/library/72411f32-d12a-4de8-b961-e54fca7faaf5)  
 [保护应用程序](/visualstudio/ide/securing-applications)  
 [保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
