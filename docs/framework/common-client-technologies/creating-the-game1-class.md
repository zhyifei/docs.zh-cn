---
title: "Creating the Game1 Class | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# Creating the Game1 Class
与所有的 Microsoft XNA 项目相同， Game1 类派生自 [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) 类，该类提供了 XNA 游戏的基本的图形设备初始化、游戏逻辑和呈现代码。  Game1 类相对简单，因为大部分工作是在 GamePiece 和 GamePieceCollection 类中完成的。  
  
## 创建代码  
 类的私有成员包括用于保存游戏块的 **GamePieceCollection** 对象、[GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) 对象和用于呈现游戏块的 [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) 对象。  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 在游戏初始化期间，这些对象被实例化。  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 当调用 [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) 方法时，则会创建游戏块并将其分配到 **GamePieceCollection** 对象。  有以下两种类型的游戏块。  略微更改这些游戏块的缩放比例，以便小块和大块同时存在。  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 游戏正在运行时，XNA Framework 会重复调用 [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 方法。  [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 方法调用游戏块集合上的 **ProcessInertia** 和 **UpdateFromMouse** 方法。  [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)中介绍了这些方法。  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 XNA Framework 在游戏运行时会重复调用[Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 方法。  [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 方法通过调用 **GamePieceCollection** 对象的 **Draw** 方法来执行游戏块的呈现。  [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)中介绍了这些方法。  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## 请参阅  
 [Manipulations and Inertia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)   
 [Using Manipulations and Inertia in an XNA Application](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)   
 [Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)   
 [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)   
 [Full Code Listings](../../../docs/framework/common-client-technologies/full-code-listings.md)