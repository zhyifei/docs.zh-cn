---
title: "如何：创建简单绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a61844f917539f5d5e7c99299c8a33f4aa18450f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="20f99-102">如何：创建简单绑定</span><span class="sxs-lookup"><span data-stu-id="20f99-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="20f99-103">此示例演示如何创建一个简单<xref:System.Windows.Data.Binding>。</span><span class="sxs-lookup"><span data-stu-id="20f99-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20f99-104">示例</span><span class="sxs-lookup"><span data-stu-id="20f99-104">Example</span></span>  
 <span data-ttu-id="20f99-105">在此示例中，你有`Person`具有名为的字符串属性对象`PersonName`。</span><span class="sxs-lookup"><span data-stu-id="20f99-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="20f99-106">`Person`对象在调用的命名空间中定义`SDKSample`。</span><span class="sxs-lookup"><span data-stu-id="20f99-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="20f99-107">下面的示例实例化`Person`对象`PersonName`属性值`Joe`。</span><span class="sxs-lookup"><span data-stu-id="20f99-107">The following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="20f99-108">将执行此操作`Resources`部分并分配`x:Key`。</span><span class="sxs-lookup"><span data-stu-id="20f99-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xaml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 <span data-ttu-id="20f99-109">若要将绑定到`PersonName`属性，你将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="20f99-109">To bind to the `PersonName` property you would do the following:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="20f99-110">因此，<xref:System.Windows.Controls.TextBlock>出现包含值"Joe"。</span><span class="sxs-lookup"><span data-stu-id="20f99-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f99-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20f99-111">See Also</span></span>  
 [<span data-ttu-id="20f99-112">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="20f99-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="20f99-113">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="20f99-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
