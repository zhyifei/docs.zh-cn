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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198434"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a>如何：测试 Point4D 结构是否相等和不相等
此示例显示了如何测试<xref:System.Windows.Media.Media3D.Point4D>结构是否相等和不相等。  
  
 下面的代码演示如何测试<xref:System.Windows.Media.Media3D.Point4D>结构是否相等和不相等使用<xref:System.Windows.Media.Media3D.Point4D>相等性的方法。  <xref:System.Windows.Media.Media3D.Point4D>结构测试相等性使用重载的等式 (`==`) 运算符，然后使用重载的不相等的不相等 (`!=`) 运算符，并最后<xref:System.Windows.Media.Media3D.Point3D>结构和一个<xref:System.Windows.Media.Media3D.Point4D>使用静态相等性检查结构<xref:System.Windows.Media.Media3D.Point4D.Equals%2A>方法。  
  
## <a name="example"></a>示例  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
