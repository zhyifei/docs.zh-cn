---
title: "Using Manipulations and Inertia in an XNA Application | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# Using Manipulations and Inertia in an XNA Application
本文介绍如何在 Microsoft XNA 应用程序中使用操作和惯性处理来控制游戏块的移动。  在阅读本文之前，应熟悉[Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)主题以及基本的 XNA 编程概念。  
  
 若要执行本文所述的任务，你的 XNA 项目必须引用 <xref:System.Windows.Input.Manipulations> 程序集，且必须在计算机上安装 [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx)（[下载地址](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)），以便你的项目可以引用 XNA 程序集。  
  
## 功能概述  
 本文介绍了如何创建表示游戏块（该游戏块使用操作和惯性处理）的自定义类。  此类使你能通过用鼠标拖动然后释放游戏块，在屏幕上操作游戏块。  一旦释放，惯性处理在游戏块逐渐减速的过程中使其保持移动。  移动是线性的和具有角度的。  
  
 ![一个简单的操作和惯性应用程序。](../../../docs/framework/common-client-technologies/media/ndp-gamexna.png "NDP\_GameXna")  
  
 此外，创建了一个自定义集合，用于管理多个游戏块。  这简化了 XNA 游戏类所需的处理。  
  
 [Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [Full Code Listings](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## 请参阅  
 <xref:System.Windows.Input.Manipulations>   
 [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)