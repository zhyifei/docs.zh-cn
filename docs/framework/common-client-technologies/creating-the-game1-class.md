---
title: "创建 Game1 类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7453c4f650e2dcadd3b8fac27b66f4db97fa0136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-game1-class"></a><span data-ttu-id="e93e0-102">创建 Game1 类</span><span class="sxs-lookup"><span data-stu-id="e93e0-102">Creating the Game1 Class</span></span>
<span data-ttu-id="e93e0-103">在所有的 Microsoft XNA 项目中，Game1 类都派生自 [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) 类，后者提供了 XNA 游戏的基本图形设备初始化、游戏逻辑和呈现代码。</span><span class="sxs-lookup"><span data-stu-id="e93e0-103">As with all Microsoft XNA projects, the Game1 class derives from the [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) class, which provides basic graphics device initialization, game logic, and rendering code for XNA games.</span></span> <span data-ttu-id="e93e0-104">Game1 类相对简单，因为大部分工作是在 GamePiece 和 GamePieceCollection 类中完成的。</span><span class="sxs-lookup"><span data-stu-id="e93e0-104">The Game1 class is fairly simple because most of the work in done in the GamePiece and GamePieceCollection classes.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="e93e0-105">创建代码</span><span class="sxs-lookup"><span data-stu-id="e93e0-105">Creating the Code</span></span>  
 <span data-ttu-id="e93e0-106">该类的私有成员包括用于保存游戏块的 GamePieceCollection 对象、[GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) 对象和用于呈现游戏块的 [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e93e0-106">The private members for the class consist of a **GamePieceCollection** object to hold the game pieces, a [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) object, and a [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) object used to render game pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 <span data-ttu-id="e93e0-107">在游戏初始化期间，这些对象被实例化。</span><span class="sxs-lookup"><span data-stu-id="e93e0-107">During game initialization, these objects are instantiated.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 <span data-ttu-id="e93e0-108">调用 [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) 方法时，会创建游戏块并将其分配给 GamePieceCollection 对象。</span><span class="sxs-lookup"><span data-stu-id="e93e0-108">When the [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) method is called, the game pieces are created and assigned to the **GamePieceCollection** object.</span></span> <span data-ttu-id="e93e0-109">有以下两种类型的游戏块。</span><span class="sxs-lookup"><span data-stu-id="e93e0-109">There are two types of game pieces.</span></span> <span data-ttu-id="e93e0-110">略微更改这些游戏块的缩放比例，以便小块和大块同时存在。</span><span class="sxs-lookup"><span data-stu-id="e93e0-110">The scale factor for the pieces is changed slightly so that there are some smaller and some larger pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 <span data-ttu-id="e93e0-111">游戏运行时，XNA Framework 会反复调用 [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="e93e0-111">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method is called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="e93e0-112">[Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 方法会对游戏块集合调用 **ProcessInertia** 和 **UpdateFromMouse** 方法。</span><span class="sxs-lookup"><span data-stu-id="e93e0-112">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method calls the **ProcessInertia** and the **UpdateFromMouse** methods on the game piece collection.</span></span> <span data-ttu-id="e93e0-113">[创建 GamePieceCollection 类](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)中介绍了这些方法。</span><span class="sxs-lookup"><span data-stu-id="e93e0-113">These methods are described in [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 <span data-ttu-id="e93e0-114">游戏运行时，XNA Framework 也会反复调用 [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="e93e0-114">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method is also called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="e93e0-115">[Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 方法通过调用 GamePieceCollection 对象的 Draw 方法来呈现游戏块。</span><span class="sxs-lookup"><span data-stu-id="e93e0-115">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method performs the rendering of game pieces by calling the **Draw** method of the **GamePieceCollection** object.</span></span> <span data-ttu-id="e93e0-116">[创建 GamePieceCollection 类](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)中介绍了这些方法。</span><span class="sxs-lookup"><span data-stu-id="e93e0-116">This method is described in[Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a><span data-ttu-id="e93e0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e93e0-117">See Also</span></span>  
 [<span data-ttu-id="e93e0-118">控制和惯性</span><span class="sxs-lookup"><span data-stu-id="e93e0-118">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="e93e0-119">在 XNA 应用程序中使用控制和惯性</span><span class="sxs-lookup"><span data-stu-id="e93e0-119">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="e93e0-120">创建 GamePiece 类</span><span class="sxs-lookup"><span data-stu-id="e93e0-120">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="e93e0-121">创建 GamePieceCollection 类</span><span class="sxs-lookup"><span data-stu-id="e93e0-121">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [<span data-ttu-id="e93e0-122">完整代码清单</span><span class="sxs-lookup"><span data-stu-id="e93e0-122">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
