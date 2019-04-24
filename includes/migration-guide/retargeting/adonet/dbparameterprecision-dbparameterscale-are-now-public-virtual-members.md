---
ms.openlocfilehash: 1721d32f8cdc9b6ea4b4732e38afa56a8a532600
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59234615"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>DbParameter.Precision 和 DbParameter.Scale 现在是公共虚拟成员

|   |   |
|---|---|
|详细信息|实现 <xref:System.Data.Common.DbParameter.Precision> 和 <xref:System.Data.Common.DbParameter.Scale> 将实现为公共虚拟属性。 它们替换相应的显示接口实现、<xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> 和 <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>。|
|建议|在重新生成 ADO.NET 数据库提供程序时，这些差异要求将“override”关键字应用到 Precision 和 Scale 属性。 仅在重新生成组件时才需要这样做；现有二进制文件将继续运行。|
|范围|次要|
|版本|4.5.1|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType></li></ul>|
