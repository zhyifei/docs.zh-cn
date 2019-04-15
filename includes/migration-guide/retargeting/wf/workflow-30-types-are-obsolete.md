---
ms.openlocfilehash: 70acbb571921c5f72ecaa26b26136a77532ad220
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234616"
---
### <a name="workflow-30-types-are-obsolete"></a>WorkFlow 3.0 类型已过时

|   |   |
|---|---|
|详细信息|Windows Workflow Foundation (WWF) 3.0 API（来自于 System.Workflow 命名空间）现已过时。|
|建议|应改用新的 WWF 4.0 API（在 System.Activities 中）。 可在[此处](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)找到使用新 API 的示例，[此处](https://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx)还提供更深入的指导。 或者，由于仍然支持 WWF 3.0 API，因此可能会使用它们，通过禁止显示生成时警告或使用较旧的编译器可以避免出现该警告。|
|范围|主要|
|版本|4.5|
|类型|重定目标|
