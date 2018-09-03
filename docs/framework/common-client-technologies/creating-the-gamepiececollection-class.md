---
title: 创建 GamePieceCollection 类
ms.date: 03/30/2017
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
ms.openlocfilehash: 6323122735273f77bfe9d61bf2df84cabe3e5d6c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43395836"
---
# <a name="creating-the-gamepiececollection-class"></a>创建 GamePieceCollection 类
GamePieceCollection 类派生自泛型 List 类，并引入可更轻松管理多个 GamePiece 对象的方法。  
  
## <a name="creating-the-code"></a>创建代码  
 GamePieceCollection 类的构造函数会初始化私有成员 capturedIndex。 此字段用于跟踪当前具有鼠标捕获的游戏块。  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 ProcessInertia 和 Draw方法通过枚举集合中的所有游戏块和对每个 GamePiece 对象调用相应的方法，简化了游戏 [Game.Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 和 [Game.Draw](https://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 方法中所需的代码。  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 游戏更新期间也会调用 UpdateFromMouse 方法。 它使只有一个游戏块可通过先检查当前捕获（若有）是否仍然有效拥有鼠标捕获。 如果有效，则不允许其他游戏块检查捕获。  
  
 如果当前任何游戏块均不具有捕获，则 UpdateFromMouse 方法将从后到前枚举每个游戏块，并检查该游戏块是否报告鼠标捕获。 如果是，则此游戏块成为当前捕获的块，并且不再进行其他处理。 UpdateFromMouse 方法首先检查集合中的最后一项，所以如果两个游戏块重叠，Z 顺序更高的游戏块将获取捕获。 Z 顺序既不是显式且不可更改；它仅由游戏添加至集合的顺序控制。  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a>请参阅  
 [控制和惯性](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [在 XNA 应用程序中使用控制和惯性](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [创建 GamePiece 类](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [创建 Game1 类](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
 [完整代码清单](../../../docs/framework/common-client-technologies/full-code-listings.md)
