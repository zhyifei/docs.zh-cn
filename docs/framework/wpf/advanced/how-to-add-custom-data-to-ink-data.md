---
title: 如何：向墨迹数据添加自定义数据
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 7c59a205df5358daec101339cc6a308c8e38a9d6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64640872"
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="d3b82-102">如何：向墨迹数据添加自定义数据</span><span class="sxs-lookup"><span data-stu-id="d3b82-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="d3b82-103">可以将自定义数据添加到手写内容保存为墨迹序列化格式 (ISF) 时将保存的墨迹。</span><span class="sxs-lookup"><span data-stu-id="d3b82-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="d3b82-104">您可以自定义将数据保存到<xref:System.Windows.Ink.DrawingAttributes>，则<xref:System.Windows.Ink.StrokeCollection>，或<xref:System.Windows.Ink.Stroke>。</span><span class="sxs-lookup"><span data-stu-id="d3b82-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="d3b82-105">能够将自定义数据保存在三个对象上使你能够决定保存数据的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="d3b82-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="d3b82-106">所有三个类使用类似的方法来存储和访问自定义数据。</span><span class="sxs-lookup"><span data-stu-id="d3b82-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="d3b82-107">只能使用以下类型可以另存为自定义数据：</span><span class="sxs-lookup"><span data-stu-id="d3b82-107">Only the following types can be saved as custom data:</span></span>  
  
- <xref:System.Boolean>  
  
- <span data-ttu-id="d3b82-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-108"><xref:System.Boolean>[]</span></span>  
  
- <xref:System.Byte>  
  
- <span data-ttu-id="d3b82-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-109"><xref:System.Byte>[]</span></span>  
  
- <xref:System.Char>  
  
- <span data-ttu-id="d3b82-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-110"><xref:System.Char>[]</span></span>  
  
- <xref:System.DateTime>  
  
- <span data-ttu-id="d3b82-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-111"><xref:System.DateTime>[]</span></span>  
  
- <xref:System.Decimal>  
  
- <span data-ttu-id="d3b82-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-112"><xref:System.Decimal>[]</span></span>  
  
- <xref:System.Double>  
  
- <span data-ttu-id="d3b82-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-113"><xref:System.Double>[]</span></span>  
  
- <xref:System.Int16>  
  
- <span data-ttu-id="d3b82-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-114"><xref:System.Int16>[]</span></span>  
  
- <xref:System.Int32>  
  
- <span data-ttu-id="d3b82-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-115"><xref:System.Int32>[]</span></span>  
  
- <xref:System.Int64>  
  
- <span data-ttu-id="d3b82-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-116"><xref:System.Int64>[]</span></span>  
  
- <xref:System.Single>  
  
- <span data-ttu-id="d3b82-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-117"><xref:System.Single>[]</span></span>  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <span data-ttu-id="d3b82-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-118"><xref:System.UInt16>[]</span></span>  
  
- <xref:System.UInt32>  
  
- <span data-ttu-id="d3b82-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-119"><xref:System.UInt32>[]</span></span>  
  
- <xref:System.UInt64>  
  
- <span data-ttu-id="d3b82-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="d3b82-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3b82-121">示例</span><span class="sxs-lookup"><span data-stu-id="d3b82-121">Example</span></span>  
 <span data-ttu-id="d3b82-122">下面的示例演示如何添加和检索自定义数据<xref:System.Windows.Ink.StrokeCollection>。</span><span class="sxs-lookup"><span data-stu-id="d3b82-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="d3b82-123">下面的示例创建一个显示应用程序<xref:System.Windows.Controls.InkCanvas>和两个按钮。</span><span class="sxs-lookup"><span data-stu-id="d3b82-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="d3b82-124">按钮， `switchAuthor`，使两个笔使用由两个不同的作者。</span><span class="sxs-lookup"><span data-stu-id="d3b82-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="d3b82-125">按钮`changePenColors`上的更改的每个笔画颜色<xref:System.Windows.Controls.InkCanvas>根据作者。</span><span class="sxs-lookup"><span data-stu-id="d3b82-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="d3b82-126">应用程序定义了两个<xref:System.Windows.Ink.DrawingAttributes>对象，并将自定义属性添加到指示哪个作者绘制每个<xref:System.Windows.Ink.Stroke>。</span><span class="sxs-lookup"><span data-stu-id="d3b82-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="d3b82-127">当用户单击`changePenColors`，应用程序更改自定义属性的值根据笔画的外观。</span><span class="sxs-lookup"><span data-stu-id="d3b82-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
