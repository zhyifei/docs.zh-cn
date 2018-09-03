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
# <a name="creating-the-gamepiececollection-class"></a><span data-ttu-id="bf5df-102">创建 GamePieceCollection 类</span><span class="sxs-lookup"><span data-stu-id="bf5df-102">Creating the GamePieceCollection Class</span></span>
<span data-ttu-id="bf5df-103">GamePieceCollection 类派生自泛型 List 类，并引入可更轻松管理多个 GamePiece 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="bf5df-103">The **GamePieceCollection** class derives from the generic List class, and introduces methods to more easily manage multiple **GamePiece** objects.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="bf5df-104">创建代码</span><span class="sxs-lookup"><span data-stu-id="bf5df-104">Creating the Code</span></span>  
 <span data-ttu-id="bf5df-105">GamePieceCollection 类的构造函数会初始化私有成员 capturedIndex。</span><span class="sxs-lookup"><span data-stu-id="bf5df-105">The constructor of the **GamePieceCollection** class initializes the private member *capturedIndex*.</span></span> <span data-ttu-id="bf5df-106">此字段用于跟踪当前具有鼠标捕获的游戏块。</span><span class="sxs-lookup"><span data-stu-id="bf5df-106">This field is used to track which of the game pieces currently has the mouse capture.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 <span data-ttu-id="bf5df-107">ProcessInertia 和 Draw方法通过枚举集合中的所有游戏块和对每个 GamePiece 对象调用相应的方法，简化了游戏 [Game.Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 和 [Game.Draw](https://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 方法中所需的代码。</span><span class="sxs-lookup"><span data-stu-id="bf5df-107">The **ProcessInertia** and the **Draw** methods simplify the code needed in the game [Game.Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) and [Game.Draw](https://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) methods by enumerating all of the game pieces in the collection and calling the respective method on each **GamePiece** object.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 <span data-ttu-id="bf5df-108">游戏更新期间也会调用 UpdateFromMouse 方法。</span><span class="sxs-lookup"><span data-stu-id="bf5df-108">The **UpdateFromMouse** method is also called during game update.</span></span> <span data-ttu-id="bf5df-109">它使只有一个游戏块可通过先检查当前捕获（若有）是否仍然有效拥有鼠标捕获。</span><span class="sxs-lookup"><span data-stu-id="bf5df-109">It enables only one game piece to have the mouse capture by first checking to see if the current capture (if any) is still in effect.</span></span> <span data-ttu-id="bf5df-110">如果有效，则不允许其他游戏块检查捕获。</span><span class="sxs-lookup"><span data-stu-id="bf5df-110">If so, no other piece is allowed to check for capture.</span></span>  
  
 <span data-ttu-id="bf5df-111">如果当前任何游戏块均不具有捕获，则 UpdateFromMouse 方法将从后到前枚举每个游戏块，并检查该游戏块是否报告鼠标捕获。</span><span class="sxs-lookup"><span data-stu-id="bf5df-111">If no piece currently has the capture, the **UpdateFromMouse** method enumerates each game piece from last to first, and checks to see if that piece reports a mouse capture.</span></span> <span data-ttu-id="bf5df-112">如果是，则此游戏块成为当前捕获的块，并且不再进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="bf5df-112">If so, that piece becomes the current captured piece, and no further processing takes place.</span></span> <span data-ttu-id="bf5df-113">UpdateFromMouse 方法首先检查集合中的最后一项，所以如果两个游戏块重叠，Z 顺序更高的游戏块将获取捕获。</span><span class="sxs-lookup"><span data-stu-id="bf5df-113">The **UpdateFromMouse** method checks the last item in the collection first so that if two pieces are overlapped, the one with the higher Z-order will obtain the capture.</span></span> <span data-ttu-id="bf5df-114">Z 顺序既不是显式且不可更改；它仅由游戏添加至集合的顺序控制。</span><span class="sxs-lookup"><span data-stu-id="bf5df-114">Z-order is not explicit nor changeable; it is governed simply by the order in which game pieces are added to the collection.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a><span data-ttu-id="bf5df-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf5df-115">See Also</span></span>  
 [<span data-ttu-id="bf5df-116">控制和惯性</span><span class="sxs-lookup"><span data-stu-id="bf5df-116">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="bf5df-117">在 XNA 应用程序中使用控制和惯性</span><span class="sxs-lookup"><span data-stu-id="bf5df-117">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="bf5df-118">创建 GamePiece 类</span><span class="sxs-lookup"><span data-stu-id="bf5df-118">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="bf5df-119">创建 Game1 类</span><span class="sxs-lookup"><span data-stu-id="bf5df-119">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
 [<span data-ttu-id="bf5df-120">完整代码清单</span><span class="sxs-lookup"><span data-stu-id="bf5df-120">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
