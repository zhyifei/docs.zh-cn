---
title: 窗体和验证
description: 了解如何在 Blazor 中通过客户端验证生成窗体。
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: c30db5e06d36a6d15301835fe782b21058a80592
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841953"
---
# <a name="forms-and-validation"></a>窗体和验证

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.NET Web 窗体框架包含一组验证服务器控件，这些控件可处理输入到窗体中的验证用户输入（`RequiredFieldValidator`、`CompareValidator`、`RangeValidator`，等等）。 ASP.NET Web 窗体框架还支持模型绑定，并基于数据批注（`[Required]`、`[StringLength]`、`[Range]`等）验证模型。 使用基于 JavaScript 的非强制验证，可以在服务器和客户端上强制实施验证逻辑。 `ValidationSummary` 服务器控件用于向用户显示验证错误的摘要。

Blazor 支持在客户端和服务器之间共享验证逻辑。 ASP.NET 提供了许多常见服务器验证的预构建 JavaScript 实现。 在许多情况下，开发人员仍需编写 JavaScript 来完全实现应用程序特定的验证逻辑。 可以在服务器和客户端上使用相同的模型类型、数据注释和验证逻辑。

Blazor 提供一组输入组件。 输入组件会将绑定字段数据处理到模型，并在提交窗体时验证用户输入。

|输入组件|呈现的 HTML 元素    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

`EditForm` 组件通过 `EditContext`包装这些输入组件并协调验证过程。 创建 `EditForm`时，可以使用 `Model` 参数指定要绑定到的模型实例。 验证通常是使用数据批注完成的，并且可以进行扩展。 若要启用基于数据批注的验证，请将 `DataAnnotationsValidator` 组件添加为 `EditForm`的子组件。 `EditForm` 组件提供了一个用于处理有效（`OnValidSubmit`）和无效（`OnInvalidSubmit`）提交的方便事件。 还有一个更通用的 `OnSubmit` 事件，可让你自行触发和处理验证。

若要显示验证错误摘要，请使用 `ValidationSummary` 组件。 若要显示特定输入字段的验证消息，请使用 `ValidationMessage` 组件，并为指向相应模型成员的 `For` 参数指定 lambda 表达式。

以下模型类型使用数据批注定义了若干验证规则：

```csharp
using System;
using System.ComponentModel.DataAnnotations;

public class Starship
{
    [Required]
    [StringLength(16,
        ErrorMessage = "Identifier too long (16 character limit).")]
    public string Identifier { get; set; }

    public string Description { get; set; }

    [Required]
    public string Classification { get; set; }

    [Range(1, 100000,
        ErrorMessage = "Accommodation invalid (1-100000).")]
    public int MaximumAccommodation { get; set; }

    [Required]
    [Range(typeof(bool), "true", "true",
        ErrorMessage = "This form disallows unapproved ships.")]
    public bool IsValidatedDesign { get; set; }

    [Required]
    public DateTime ProductionDate { get; set; }
}
```

以下组件演示如何基于 `Starship` 模型类型在 Blazor 中生成窗体：

```razor
<h1>New Ship Entry Form</h1>

<EditForm Model="@starship" OnValidSubmit="@HandleValidSubmit">
    <DataAnnotationsValidator />
    <ValidationSummary />

    <p>
        <label for="identifier">Identifier: </label>
        <InputText id="identifier" @bind-Value="starship.Identifier" />
        <ValidationMessage For="() => starship.Identifier" />
    </p>
    <p>
        <label for="description">Description (optional): </label>
        <InputTextArea id="description" @bind-Value="starship.Description" />
    </p>
    <p>
        <label for="classification">Primary Classification: </label>
        <InputSelect id="classification" @bind-Value="starship.Classification">
            <option value="">Select classification ...</option>
            <option value="Exploration">Exploration</option>
            <option value="Diplomacy">Diplomacy</option>
            <option value="Defense">Defense</option>
        </InputSelect>
        <ValidationMessage For="() => starship.Classification" />
    </p>
    <p>
        <label for="accommodation">Maximum Accommodation: </label>
        <InputNumber id="accommodation" @bind-Value="starship.MaximumAccommodation" />
        <ValidationMessage For="() => starship.MaximumAccommodation" />
    </p>
    <p>
        <label for="valid">Engineering Approval: </label>
        <InputCheckbox id="valid" @bind-Value="starship.IsValidatedDesign" />
        <ValidationMessage For="() => starship.IsValidatedDesign" />
    </p>
    <p>
        <label for="productionDate">Production Date: </label>
        <InputDate id="productionDate" @bind-Value="starship.ProductionDate" />
        <ValidationMessage For="() => starship.ProductionDate" />
    </p>

    <button type="submit">Submit</button>
</EditForm>

@code {
    private Starship starship = new Starship();

    private void HandleValidSubmit()
    {
        // Save the data
    }
}
```

提交窗体后，不会将模型绑定的数据保存到任何数据存储，如数据库。 在 Blazor WebAssembly 应用程序中，必须将数据发送到服务器。 例如，使用 HTTP POST 请求。 在 Blazor 服务器应用中，数据已在服务器上，但必须持久保存。 处理 Blazor apps 中的数据访问是处理[数据](data.md)部分的主题。

## <a name="additional-resources"></a>其他资源

有关 Blazor 应用中[表单和验证](/aspnet/core/blazor/forms-validation)的详细信息，请参阅 Blazor 文档。

>[!div class="step-by-step"]
>[上一页](state-management.md)
>[下一页](data.md)
