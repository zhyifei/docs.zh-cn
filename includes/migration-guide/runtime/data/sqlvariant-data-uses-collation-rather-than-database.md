---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235148"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a>Sql_variant 数据使用 sql_variant 排序规则而不是数据库排序规则

|   |   |
|---|---|
|详细信息|<code>sql_variant</code> 数据使用 <code>sql_variant</code> 排序规则而不是数据库排序规则。|
|建议|如果数据库排序规则与 <code>sql_variant</code> 排序规则不同，则此更改将解决可能的数据损坏。 依赖损坏的数据的应用程序可能会失败。|
|范围|透明|
|Version|4.5|
|类型|运行时|
