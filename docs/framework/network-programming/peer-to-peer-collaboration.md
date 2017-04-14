---
title: "对等协作 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: b6216d88-bccb-4a59-9f1c-9f751708e811
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# 对等协作
对网络连接位于Internet边缘更多的基于客户端的计算任务相对强大的计算机\(PC\)的使用率。  现代PC \(PC\)具有非常快处理器、浩大的内存和一个大硬盘，不完全使用任何一个，当执行常见计算的任务\(如扫描时的电子邮件和的Web。  现代PC可以轻松地为客户端和服务器\(对等项\)应用程序的许多类型的。  
  
-   对协作基础结构是在Windows vista和更高版本平台利用网络邻近services Microsoft Windows对基础结构的一个简化的实现。  它最适用于在网络邻近服务操作的子网中的对等类启用的应用程序使用，不过，它可以internet服务终结点或与。  它包含Live Messenger和其他活动识别应用程序使用确定联系人终结点、可用性和存在的常见交际管理者软件。  
  
## 协作应用程序  
 典型的对协作应用程序包括以下步骤:  
  
-   对等类确定是承载协作会话希望对等类的标识  
  
-   发送请求承载会话，在某种程度上，因此，宿主对等类授予管理协作事件。  
  
-   宿主邀请在子网的联系人（包括申请者）到会话。  
  
-   若要协作的所有对等类可以将宿主到其交际管理者软件。  
  
-   大多数对等类是否将发送此响应，接受或拒绝，立即回主对等类。  
  
-   若要协作的所有对等类将订阅到宿主对等类。  
  
-   当对等类执行其初始协作事件时，宿主对等类可以添加远程对等类到其交际管理者软件。  它还处理所有邀请响应确定谁接受的，拒绝，因此，未响应。  它可以取消此调用到非答案的人员，或者执行一些其他操作。  
  
-   此时，宿主对等类可以开始使用任何受邀请对等类或注册的协作会话与协作基础结构的应用程序。  P2P应用程序使用对协作基础结构和 <xref:System.Net.PeerToPeer.Collaboration> 命名空间协调游戏、公告板、会话和其他serverless存在应用程序的通信。  
  
## 对网络安全  
 使用Kerberos，在Active Directory域，则域控制器提供身份验证服务。  在一个serverless对等类环境中，对等类必须提供自己的身份验证。  为对网络连接，所有节点可用作CA，移除根证书的要求在每对等类受信任的根存储区。  使用自签名证书，身份验证提供，格式化为X.509证书。  这些是使用私钥，由每对等类创建，生成公钥\/私钥对和证书签名的证书。  自签名证书进行身份验证使用并提供有关对实体的信息。  与X.509身份验证，对等类网络身份验证取决于跟踪回信任的公钥的证书链。  
  
## 请参阅  
 <xref:System.Net.PeerToPeer.Collaboration>   
 [关于 System.Net.PeerToPeer.Collaboration 命名空间](../../../docs/framework/network-programming/about-the-system-net-peertopeer-collaboration-namespace.md)