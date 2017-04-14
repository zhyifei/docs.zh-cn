---
title: "关于 System.Net.PeerToPeer.Collaboration 命名空间 | Microsoft Docs"
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
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# 关于 System.Net.PeerToPeer.Collaboration 命名空间
<xref:System.Net.PeerToPeer.Collaboration> 命名空间提供使用对协作基础结构，用于实现对等类协作事件的选件类和API。  
  
## 类  
 用于对等协作事件的实现的主类是:  
  
-   <xref:System.Net.PeerToPeer.Collaboration.ContactManager>，可用于存储对等类联系人。  
  
-   协作，例如游戏，请聊天客户端的 <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> 或会话解决方案。  
  
-   在事件协作的对等类。  这些对等类可以表示为 <xref:System.Net.PeerToPeer.Collaboration.PeerContact>、 <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>或 <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> 对象。  
  
-   静态 <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> 选件类，指定要应用程序可用，哪些对等类参与它们。  
  
 <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> 方法用于邀请对等类到协作会话。  调用对等类可以订阅通知更新对应用程序、对象或现有信息参与与协作会话的事件的另一对等类。  存在选件类指定 <xref:System.Net.PeerToPeer.Collaboration.Peer> 是否为协作可用，并且， <xref:System.Net.PeerToPeer.Collaboration.PeerScope> 选件类用于指定要参与允许对等类: <xref:System.Net.PeerToPeer.Collaboration.PeerScope> \(全局\)， <xref:System.Net.PeerToPeer.Collaboration.PeerScope>， \(子网\)或 <xref:System.Net.PeerToPeer.Collaboration.PeerScope>。  
  
 协作会话由四个步骤:  
  
-   发现。  查看或发布应用程序、对等类并显示信息。  例如，找到具有相同的游戏安装本地子网的其他人员。  
  
-   邀请。  发送并接受远程对等类的安全邀请启动或连接 <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> 会话。  
  
-   联系人管理。  添加发现了对等类作为联系人到 <xref:System.Net.PeerToPeer.Collaboration.ContactManager>。  
  
-   通信。  当通信建立时，请使用 <xref:System.Net> API， <xref:System.Net.PeerToPeer> API，或Windows communication foundation对等类必须为多一方的通信类别。  
  
 例如，宿主对等类启动协作会话，并使用 <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> 方法添加远程对等类和一个本地对等类到宿主对等类的交际管理者软件。  三个用户随后将参与它们的私有协作会话。  
  
 典型的P2P应用程序是:为协作说明采用confidence或whiteboarding， serverless聊天应用程序、interactive广告和联机赌博会话。  
  
## 请参阅  
 <xref:System.Net.PeerToPeer.Collaboration>