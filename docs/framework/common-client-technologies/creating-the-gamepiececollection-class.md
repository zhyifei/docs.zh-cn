---
title: "创建 GamePieceCollection 类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f000c1eed27acc16d158cb893cba876ea016277
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-gamepiececollection-class"></a><span data-ttu-id="1cab5-102">创建 GamePieceCollection 类</span><span class="sxs-lookup"><span data-stu-id="1cab5-102">Creating the GamePieceCollection Class</span></span>
<span data-ttu-id="1cab5-103">GamePieceCollection 类派生自泛型 List 类，并引入可更轻松管理多个 GamePiece 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="1cab5-103">The **GamePieceCollection** class derives from the generic List class, and introduces methods to more easily manage multiple **GamePiece** objects.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="1cab5-104">创建代码</span><span class="sxs-lookup"><span data-stu-id="1cab5-104">Creating the Code</span></span>  
 <span data-ttu-id="1cab5-105">GamePieceCollection 类的构造函数会初始化私有成员 capturedIndex。</span><span class="sxs-lookup"><span data-stu-id="1cab5-105">The constructor of the **GamePieceCollection** class initializes the private member *capturedIndex*.</span></span> <span data-ttu-id="1cab5-106">此字段用于跟踪当前具有鼠标捕获的游戏块。</span><span class="sxs-lookup"><span data-stu-id="1cab5-106">This field is used to track which of the game pieces currently has the mouse capture.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 <span data-ttu-id="1cab5-107">ProcessInertia 和 Draw方法通过枚举集合中的所有游戏块和对每个 GamePiece 对象调用相应的方法，简化了游戏 [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 和 [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 方法中所需的代码。</span><span class="sxs-lookup"><span data-stu-id="1cab5-107">The **ProcessInertia** and the **Draw** methods simplify the code needed in the game [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) and [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) methods by enumerating all of the game pieces in the collection and calling the respective method on each **GamePiece** object.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 <span data-ttu-id="1cab5-108">游戏更新期间也会调用 UpdateFromMouse 方法。</span><span class="sxs-lookup"><span data-stu-id="1cab5-108">The **UpdateFromMouse** method is also called during game update.</span></span> <span data-ttu-id="1cab5-109">它使只有一个游戏块可通过先检查当前捕获（若有）是否仍然有效拥有鼠标捕获。</span><span class="sxs-lookup"><span data-stu-id="1cab5-109">It enables only one game piece to have the mouse capture by first checking to see if the current capture (if any) is still in effect.</span></span> <span data-ttu-id="1cab5-110">如果有效，则不允许其他游戏块检查捕获。</span><span class="sxs-lookup"><span data-stu-id="1cab5-110">If so, no other piece is allowed to check for capture.</span></span>  
  
 <span data-ttu-id="1cab5-111">如果当前任何游戏块均不具有捕获，则 UpdateFromMouse 方法将从后到前枚举每个游戏块，并检查该游戏块是否报告鼠标捕获。</span><span class="sxs-lookup"><span data-stu-id="1cab5-111">If no piece currently has the capture, the **UpdateFromMouse** method enumerates each game piece from last to first, and checks to see if that piece reports a mouse capture.</span></span> <span data-ttu-id="1cab5-112">如果是，则此游戏块成为当前捕获的块，并且不再进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="1cab5-112">If so, that piece becomes the current captured piece, and no further processing takes place.</span></span> <span data-ttu-id="1cab5-113">UpdateFromMouse 方法首先检查集合中的最后一项，所以如果两个游戏块重叠，Z 顺序更高的游戏块将获取捕获。</span><span class="sxs-lookup"><span data-stu-id="1cab5-113">The **UpdateFromMouse** method checks the last item in the collection first so that if two pieces are overlapped, the one with the higher Z-order will obtain the capture.</span></span> <span data-ttu-id="1cab5-114">Z 顺序既不是显式且不可更改；它仅由游戏添加至集合的顺序控制。</span><span class="sxs-lookup"><span data-stu-id="1cab5-114">Z-order is not explicit nor changeable; it is governed simply by the order in which game pieces are added to the collection.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a><span data-ttu-id="1cab5-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cab5-115">See Also</span></span>  
 [<span data-ttu-id="1cab5-116">控制和惯性</span><span class="sxs-lookup"><span data-stu-id="1cab5-116">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="1cab5-117">在 XNA 应用程序中使用控制和惯性</span><span class="sxs-lookup"><span data-stu-id="1cab5-117">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="1cab5-118">创建 GamePiece 类</span><span class="sxs-lookup"><span data-stu-id="1cab5-118">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="1cab5-119">创建 Game1 类</span><span class="sxs-lookup"><span data-stu-id="1cab5-119">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
 [<span data-ttu-id="1cab5-120">完整代码清单</span><span class="sxs-lookup"><span data-stu-id="1cab5-120">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
