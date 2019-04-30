---
title: 如何：测试 Point4D 结构是否相等和不相等
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: ce1188e99ef2b0682427cc2e227aaccd27f7c4f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050631"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a><span data-ttu-id="a3455-102">如何：测试 Point4D 结构是否相等和不相等</span><span class="sxs-lookup"><span data-stu-id="a3455-102">How to: Test Point4D structures for equality and inequality</span></span>
<span data-ttu-id="a3455-103">此示例显示了如何测试<xref:System.Windows.Media.Media3D.Point4D>结构是否相等和不相等。</span><span class="sxs-lookup"><span data-stu-id="a3455-103">This example shows how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality.</span></span>  
  
 <span data-ttu-id="a3455-104">下面的代码演示如何测试<xref:System.Windows.Media.Media3D.Point4D>结构是否相等和不相等使用<xref:System.Windows.Media.Media3D.Point4D>相等性的方法。</span><span class="sxs-lookup"><span data-stu-id="a3455-104">The following code illustrates how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality using the <xref:System.Windows.Media.Media3D.Point4D> equality methods.</span></span>  <span data-ttu-id="a3455-105"><xref:System.Windows.Media.Media3D.Point4D>结构测试相等性使用重载的等式 (`==`) 运算符，然后使用重载的不相等的不相等 (`!=`) 运算符，并最后<xref:System.Windows.Media.Media3D.Point3D>结构和一个<xref:System.Windows.Media.Media3D.Point4D>使用静态相等性检查结构<xref:System.Windows.Media.Media3D.Point4D.Equals%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="a3455-105">The <xref:System.Windows.Media.Media3D.Point4D> structures are tested for equality using the overloaded equality (`==`) operator, then for inequality using the overloaded inequality (`!=`) operator, and finally a <xref:System.Windows.Media.Media3D.Point3D> structure and a <xref:System.Windows.Media.Media3D.Point4D> structure are checked for equality using the static <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3455-106">示例</span><span class="sxs-lookup"><span data-stu-id="a3455-106">Example</span></span>  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a><span data-ttu-id="a3455-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3455-107">See also</span></span>

- <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
