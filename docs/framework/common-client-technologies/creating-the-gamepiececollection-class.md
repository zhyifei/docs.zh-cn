---
title: "Creating the GamePieceCollection Class | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# Creating the GamePieceCollection Class
**GamePieceCollection** 类派生自泛型 List 类，并引入可更轻松管理多个 **GamePiece** 对象的方法。  
  
## 创建代码  
 **GamePieceCollection** 类的构造函数会初始化私有成员 *capturedIndex*。  此字段用于跟踪当前具有鼠标捕获的游戏块。  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 **ProcessInertia** 和 **Draw** 方法通过枚举集合中所有游戏块和在每个 **GamePiece** 对象上调用相应方法来简化游戏 [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 和 [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 方法中所需的代码。  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 **UpdateFromMouse** 方法也可在游戏更新期间进行调用。  它使只有一个游戏块可通过先检查当前捕获（若有）是否仍然有效拥有鼠标捕获。  如果有效，则不允许其他游戏块检查捕获。  
  
 如果当前游戏块均不具有捕获，则 **UpdateFromMouse** 方法将从后到前枚举每个游戏块，并检查此游戏块是否报告鼠标捕获。  如果是，则此游戏块成为当前捕获的块，并且不再进行其他处理。  **UpdateFromMouse** 方法首先检查集合中的最后一项，以使如果两个游戏块重叠， Z 顺序更高的游戏块将获取捕获。  Z 顺序既不是显式且不可更改；它仅由游戏添加至集合的顺序控制。  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## 请参阅  
 [Manipulations and Inertia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)   
 [Using Manipulations and Inertia in an XNA Application](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)   
 [Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)   
 [Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)   
 [Full Code Listings](../../../docs/framework/common-client-technologies/full-code-listings.md)