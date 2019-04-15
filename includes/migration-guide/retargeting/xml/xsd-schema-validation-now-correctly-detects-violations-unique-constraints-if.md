---
ms.openlocfilehash: 5844dbc2c3c89baeb39b69f16846f92ac10e97f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234357"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>如果使用复合密钥并且一个密钥为空，XSD 架构验证现在可正确检测是否违反唯一约束

|   |   |
|---|---|
|详细信息|在版本 4.6 之前的 .NET Framework 版本中存在一个 bug，即如果其中一个密钥为空，XSD 验证无法检测复合密钥上的唯一约束。 在 .NET Framework 4.6 中，此问题已得到更正。 这将导致更多的正确验证，但也可能导致无法像以前版本那样验证某些 XML。|
|建议|如果需要更宽松的 .NET Framework 4.0 验证，该验证应用程序可以面向版本 4.5（或更早版本）的 .NET Framework。 但在重定向到 .NET Framework 4.6 时，应执行代码评审，确保无需验证重复的复合密钥（如在此问题的描述中所述）。|
|范围|边缘|
|版本|4.6|
|类型|重定目标|
