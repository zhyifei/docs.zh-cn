---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379524"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>对于 System.Drawing，WinForm 的 CheckForOverflowUnderflow 属性现在为 true

|   |   |
|---|---|
|详细信息|System.Drawing.dll 程序集的 CheckForOverflowUnderflow 设置为 true。|
|建议|之前在发生溢出时，结果会在不提示的情况下被截断。 现在引发了 <xref:System.OverflowException?displayProperty=name> 异常。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
