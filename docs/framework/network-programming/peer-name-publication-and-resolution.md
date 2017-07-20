---
title: "对等名称发布和解析 | Microsoft Docs"
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
ms.assetid: f0370e08-9fa6-4ee5-ab78-9a58a20a7da2
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# 对等名称发布和解析
## 发布对等类名称  
 若要发布一个新PNRP ID，对等类执行以下操作:  
  
-   发送PNRP发布信息。注册了最低级别的PNRP ID缓存\)的其缓存空间量\(对等类为其缓存。  
  
-   选择不是其相邻元素中的朵云的任意节点并将其发送PNRP名称解析请求自己的P2P ID.  发生的终点确定处理种子缓存在云的任意节点与发布对等类的PNRP ID。  
  
 ，如果只有解决其他P2P ID， PNRP版本2节点不发布PNRP ID。  HKEY\_LOCAL\_MACHINE \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion \\ PeerNet \\ PNRP \\ IPV6全局\\ SearchOnly\=1注册表值\(REG\_DWORD类型\)用于名称释放指定对等类只有使用PNRP用于名称转换，从未。  此注册表值可以通过组策略还配置。  
  
## 解决对等类名称  
 找到其他同级PNRP网络或云是过程由两个阶段组成:  
  
1.  终结点确定  
  
2.  PNRP ID解析  
  
 在终结点确定阶段，尝试解析对等类某项服务的PNRP ID在另一台计算机上确定该远程对等类 IPv6 地址。  远程对等类要发布的一个，或者与关联，计算机的PNRP ID或服务。  
  
 在确认之后该远程终结点注册到PNRP云， PNRP ID解析阶段的请求的对等类发送一个请求到所需服务的PNRP ID的该对等类终结点。  该终结点发送确认请求的对等类可以用于以后的通信要使用的服务、注释和4 KB的PNRP ID的答复附加信息。  例如，因此，如果所需的终点是赌博服务器，则附加对等类名称记录数据可能包含有关游戏的信息，效果的秩和玩家的当前项数。  
  
 在终结点确定阶段， PNRP使用一个迭代的说明发布PNRP ID，执行解析的节点到与节点连接负责连续更接近目标PNRP ID.的环境的节点处理  
  
 若要执行名称将PNRP，对等类在其与目标PNRP ID.项的自己的缓存检查项  如果找到，对等类发送PNRP请求消息。对等类并等待响应。  如果找不到PNRP ID的项，对等类发送PNRP请求信息到对应于项都有一个PNRP ID一个与目标PNRP ID.对等类  接收PNRP请求消息的节点检查自己的缓存并执行以下操作:  
  
-   如果找到PNRP ID，请求的终点对等类答案直接请求的对等类。  
  
-   如果找不到PNRP ID，并且一PNRP ID在缓存更接近目标PNRP ID的环境，请求的对等类发送到包含使用PNRP ID表示项对等类的 IPv6 地址的请求的对等类的响应最匹配目标PNRP ID.  使用在响应的IP地址，请求的节点发送另一PNRP请求信息为 IPv6 地址响应或检查其缓存。  
  
-   如果找不到PNRP ID，并且不PNRP ID在更接近目标PNRP ID的环境的其缓存，请求的对等类发送请求的对等类指示此情况的响应。  请求的对等类然后选择最NeXT关闭的PNRP ID.  
  
 请求的对等类继续此过程的后续迭代，最终找到注册PNRP ID.的节点  
  
 在 <xref:System.Net.PeerToPeer> 命名空间中，包含终结点和PNRP云或网格它们进行通信的 <xref:System.Net.PeerToPeer.PeerName> 记录之间的多对多关系。  当有重复或时使用 <xref:System.Net.PeerToPeer.PeerNameResolver> 选件类，过时项或多个节点具有相同的对等类名称， PNRP节点可获取当前信息。  <xref:System.Net.PeerToPeer.PeerNameResolver> 方法使用一个对等类名称简化了透视图到一个对等类对多对等类名称记录与同一一对等类为与云。  这与使用相关表执行的查询连接。  在成功完成，解析器对象返回指定的对等类名称的 <xref:System.Net.PeerToPeer.PeerNameRecordCollection> 。  例如，对等类名称在集合中的所有对等类名称日志将发生，按照云。  这些是支持数据可能由基于PNRP的应用程序请求对等类名称的实例。  
  
## 请参阅  
 <xref:System.Net.PeerToPeer>