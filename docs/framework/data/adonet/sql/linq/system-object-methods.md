---
title: System.Object 方法
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 3a52f081f1c0c6e6c5218550009c736d0ed60514
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097663"
---
# <a name="systemobject-methods"></a><span data-ttu-id="f05f1-102">System.Object 方法</span><span class="sxs-lookup"><span data-stu-id="f05f1-102">System.Object Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f05f1-103">支持以下<xref:System.Object>方法。</span><span class="sxs-lookup"><span data-stu-id="f05f1-103">supports the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f05f1-104">不支持以下<xref:System.Object>方法。</span><span class="sxs-lookup"><span data-stu-id="f05f1-104">does not support the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> <span data-ttu-id="f05f1-105">为二进制文件类型，如`BINARY`， `VARBINARY`， `IMAGE`，和`TIMESTAMP`。</span><span class="sxs-lookup"><span data-stu-id="f05f1-105">for binary types such as `BINARY`, `VARBINARY`, `IMAGE`, and `TIMESTAMP`.</span></span>||  
  
## <a name="differences-from-net"></a><span data-ttu-id="f05f1-106">与 .NET 的差异</span><span class="sxs-lookup"><span data-stu-id="f05f1-106">Differences from .NET</span></span>  
 <span data-ttu-id="f05f1-107">输出<xref:System.Object.ToString?displayProperty=nameWithType>双使用 SQL `CONVERT`(NVARCHAR(30)， @x，2) 在 SQL 上。</span><span class="sxs-lookup"><span data-stu-id="f05f1-107">The output of <xref:System.Object.ToString?displayProperty=nameWithType> for double uses SQL `CONVERT`(NVARCHAR(30), @x, 2) on SQL.</span></span> <span data-ttu-id="f05f1-108">在这种情况下 SQL 始终使用 16 位科学记数法（例如，用“0.000000000000000e+000”表示 0）。</span><span class="sxs-lookup"><span data-stu-id="f05f1-108">SQL always uses 16 digits and scientific notation in this case (for example, "0.000000000000000e+000" for 0).</span></span> <span data-ttu-id="f05f1-109">因此，<xref:System.Object.ToString?displayProperty=nameWithType> 转换与 .NET Framework 中的 <xref:System.Convert.ToString%2A?displayProperty=nameWithType> 产生的字符串不同。</span><span class="sxs-lookup"><span data-stu-id="f05f1-109">As a result, <xref:System.Object.ToString?displayProperty=nameWithType> conversion does not produce the same string as <xref:System.Convert.ToString%2A?displayProperty=nameWithType> in the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f05f1-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f05f1-110">See also</span></span>

- [<span data-ttu-id="f05f1-111">数据类型和函数</span><span class="sxs-lookup"><span data-stu-id="f05f1-111">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
