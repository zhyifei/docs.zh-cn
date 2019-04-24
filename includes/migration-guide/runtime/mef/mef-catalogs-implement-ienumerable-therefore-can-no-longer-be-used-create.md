---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803384"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>MEF 目录实现 IEnumerable，因此不能再用于创建序列化程序

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5 开始，MEF 目录实现 IEnumerable，因此不能再用于创建序列化程序（<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> 对象）。 尝试对 MEF 目录进行序列化会引发异常。|
|建议|不能再使用 MEF 创建序列化程序|
|范围|主要|
|版本|4.5|
|类型|运行时|
