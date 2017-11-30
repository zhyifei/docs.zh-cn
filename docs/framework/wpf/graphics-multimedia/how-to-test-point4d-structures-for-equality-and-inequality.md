---
title: "如何：测试 Point4D 结构是否相等和不相等"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 849082fc1b933c4172c0d22ec3c9c2a1644a32fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a><span data-ttu-id="d47d9-102">如何：测试 Point4D 结构是否相等和不相等</span><span class="sxs-lookup"><span data-stu-id="d47d9-102">How to: Test Point4D structures for equality and inequality</span></span>
<span data-ttu-id="d47d9-103">此示例演示如何测试<xref:System.Windows.Media.Media3D.Point4D>等式和不等式的结构。</span><span class="sxs-lookup"><span data-stu-id="d47d9-103">This example shows how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality.</span></span>  
  
 <span data-ttu-id="d47d9-104">下面的代码演示如何测试<xref:System.Windows.Media.Media3D.Point4D>结构的相等性和不相等使用<xref:System.Windows.Media.Media3D.Point4D>相等的方法。</span><span class="sxs-lookup"><span data-stu-id="d47d9-104">The following code illustrates how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality using the <xref:System.Windows.Media.Media3D.Point4D> equality methods.</span></span>  <span data-ttu-id="d47d9-105"><xref:System.Windows.Media.Media3D.Point4D>结构进行测试以使用重载的相等性的相等性 (`==`) 运算符，然后使用重载的不相等的不相等 (`!=`) 运算符，并最后<xref:System.Windows.Media.Media3D.Point3D>结构和<xref:System.Windows.Media.Media3D.Point4D>检查结构中的使用静态相等<xref:System.Windows.Media.Media3D.Point4D.Equals%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="d47d9-105">The <xref:System.Windows.Media.Media3D.Point4D> structures are tested for equality using the overloaded equality (`==`) operator, then for inequality using the overloaded inequality (`!=`) operator, and finally a <xref:System.Windows.Media.Media3D.Point3D> structure and a <xref:System.Windows.Media.Media3D.Point4D> structure are checked for equality using the static <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d47d9-106">示例</span><span class="sxs-lookup"><span data-stu-id="d47d9-106">Example</span></span>  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a><span data-ttu-id="d47d9-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d47d9-107">See Also</span></span>  
 <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>  
 <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>  
 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
