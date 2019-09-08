---
title: System.Object 方法
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: d1a36798ef789bbc44f581dfc631feee19e1f66b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781076"
---
# <a name="systemobject-methods"></a>System.Object 方法
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]支持以下<xref:System.Object>方法。  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 不支持以下 <xref:System.Object> 方法。  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|用于二进制类型（如 <xref:System.Object.ToString?displayProperty=nameWithType>、`BINARY`、`VARBINARY` 和 `IMAGE`）的 `TIMESTAMP`。||  
  
## <a name="differences-from-net"></a>与 .NET 的差异  
 <xref:System.Object.ToString?displayProperty=nameWithType> For double 的输出在 sql 上`CONVERT`使用 sql （NVARCHAR （30 @x），，2）。 在这种情况下 SQL 始终使用 16 位科学记数法（例如，用“0.000000000000000e+000”表示 0）。 因此，<xref:System.Object.ToString?displayProperty=nameWithType> 转换与 .NET Framework 中的 <xref:System.Convert.ToString%2A?displayProperty=nameWithType> 产生的字符串不同。  
  
## <a name="see-also"></a>请参阅

- [数据类型和函数](data-types-and-functions.md)
