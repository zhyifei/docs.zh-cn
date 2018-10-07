---
title: 声明性约束
ms.date: 03/30/2017
ms.assetid: 67001ed1-7f4d-4ada-ae57-a31176901a53
ms.openlocfilehash: 5599513405c77aa213b329b085075660baed5c47
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48842367"
---
# <a name="declarative-constraints"></a><span data-ttu-id="61964-102">声明性约束</span><span class="sxs-lookup"><span data-stu-id="61964-102">Declarative Constraints</span></span>
<span data-ttu-id="61964-103">声明性约束为活动及其与其他活动的关系提供了一个功能强大的验证方法。</span><span class="sxs-lookup"><span data-stu-id="61964-103">Declarative constraints provide a powerful method of validation for an activity and its relationships with other activities.</span></span> <span data-ttu-id="61964-104">约束是在创作过程中为活动配置的，但工作流宿主也可以指定其他约束。</span><span class="sxs-lookup"><span data-stu-id="61964-104">Constraints are configured for an activity during the authoring process, but additional constraints can also be specified by the workflow host.</span></span> <span data-ttu-id="61964-105">本主题概述了如何使用声明性约束提供活动验证。</span><span class="sxs-lookup"><span data-stu-id="61964-105">This topic provides an overview of using declarative constraints to provide activity validation.</span></span>  
  
## <a name="using-declarative-constraints"></a><span data-ttu-id="61964-106">使用声明性约束</span><span class="sxs-lookup"><span data-stu-id="61964-106">Using Declarative Constraints</span></span>  
 <span data-ttu-id="61964-107">约束是包含验证逻辑的活动。</span><span class="sxs-lookup"><span data-stu-id="61964-107">A constraint is an activity that contains validation logic.</span></span> <span data-ttu-id="61964-108">可以用代码或 XAML 创作此约束活动。</span><span class="sxs-lookup"><span data-stu-id="61964-108">This constraint activity can be authored in code or in XAML.</span></span> <span data-ttu-id="61964-109">创建约束活动之后，活动作者可将此约束添加到该活动的 <xref:System.Activities.Activity.Constraints%2A> 属性中以进行验证，或者他们也可以使用该约束通过使用 <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> 实例的 <xref:System.Activities.Validation.ValidationSettings> 属性提供其他验证。</span><span class="sxs-lookup"><span data-stu-id="61964-109">After a constraint activity is created, activity authors add this constraint to the <xref:System.Activities.Activity.Constraints%2A> property of the activity to validate, or they use the constraint to provide additional validation by using the <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> property of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="61964-110">验证逻辑可以包含简单的验证（如验证活动的元数据），也可以执行考虑当前活动与其父级、子级和同级活动的关系的验证。</span><span class="sxs-lookup"><span data-stu-id="61964-110">The validation logic can consist of simple validations such as validating an activity’s metadata, but it can also perform validation that takes into account the relationship of the current activity to its parent, children, and sibling activities.</span></span> <span data-ttu-id="61964-111"><xref:System.Activities.Validation.Constraint%601> 活动可用于创作约束，并且提供了多个其他验证活动以协助创建验证错误和警告并提供有关工作流中相关活动的信息。</span><span class="sxs-lookup"><span data-stu-id="61964-111">Constraints are authored by using the <xref:System.Activities.Validation.Constraint%601> activity, and several additional validation activities are provided to assist with the creation of validation errors and warnings and to provide information about related activities in the workflow.</span></span>  
  
### <a name="assertvalidation-and-addvalidationerror"></a><span data-ttu-id="61964-112">AssertValidation 和 AddValidationError</span><span class="sxs-lookup"><span data-stu-id="61964-112">AssertValidation and AddValidationError</span></span>  
 <span data-ttu-id="61964-113"><xref:System.Activities.Validation.AssertValidation> 活动计算其 <xref:System.Activities.Validation.AssertValidation.Assertion%2A> 属性引用的表达式，如果表达式的计算结果为 `false`，则会向 <xref:System.Activities.Validation.ValidationResults> 添加验证错误或警告。</span><span class="sxs-lookup"><span data-stu-id="61964-113">The <xref:System.Activities.Validation.AssertValidation> activity evaluates the expression referenced by its <xref:System.Activities.Validation.AssertValidation.Assertion%2A> property, and if the expression evaluates to `false`, a validation error or warning is added to the <xref:System.Activities.Validation.ValidationResults>.</span></span> <span data-ttu-id="61964-114"><xref:System.Activities.Validation.AssertValidation.Message%2A> 属性描述验证错误，<xref:System.Activities.Validation.AssertValidation.IsWarning%2A> 属性指示验证失败为错误还是警告。</span><span class="sxs-lookup"><span data-stu-id="61964-114">The <xref:System.Activities.Validation.AssertValidation.Message%2A> property describes the validation error and the <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> property indicates whether the validation failure is an error or a warning.</span></span> <span data-ttu-id="61964-115"><xref:System.Activities.Validation.AssertValidation.IsWarning%2A> 的默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="61964-115">The default value for <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> is `false`.</span></span>  
  
 <span data-ttu-id="61964-116">在下面的示例中，声明一个约束，如果验证的活动的 <xref:System.Activities.Activity.DisplayName%2A> 是两个字符或更少字符，则该约束返回一个验证警告。</span><span class="sxs-lookup"><span data-stu-id="61964-116">In the following example, a constraint is declared that returns a validation warning if the <xref:System.Activities.Activity.DisplayName%2A> of the activity being validated is two characters or less in length.</span></span> <span data-ttu-id="61964-117">用于 <xref:System.Activities.Validation.Constraint%601> 的泛型类型参数指定该约束验证的活动类型。</span><span class="sxs-lookup"><span data-stu-id="61964-117">The generic type parameter used for <xref:System.Activities.Validation.Constraint%601> specifies the type of activity that is validated by the constraint.</span></span> <span data-ttu-id="61964-118">此约束使用 <xref:System.Activities.Activity> 作为泛型类型并且可用于验证所有类型的活动。</span><span class="sxs-lookup"><span data-stu-id="61964-118">This constraint uses <xref:System.Activities.Activity> as the generic type and can be used to validate all types of activities.</span></span>  
  
```csharp  
public static Constraint ActivityDisplayNameIsNotSetWarning()  
{  
    DelegateInArgument<Activity> element = new DelegateInArgument<Activity>();  
  
    return new Constraint<Activity>  
    {  
        Body = new ActivityAction<Activity, ValidationContext>  
        {  
            Argument1 = element,  
            Handler = new AssertValidation  
            {  
                IsWarning = true,  
                Assertion = new InArgument<bool>(env => (element.Get(env).DisplayName.Length > 2)),  
                Message = new InArgument<string>("It is a best practice to have a DisplayName of more than 2 characters."),  
            }  
        }  
    };  
}  
```  
  
 <span data-ttu-id="61964-119">若要为某个活动指定此约束，请将其添加到该活动的 <xref:System.Activities.Activity.Constraints%2A> 中，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="61964-119">To specify this constraint for an activity, it is added to the <xref:System.Activities.Activity.Constraints%2A> of the activity, as shown in the following example code.</span></span>  
  
```csharp  
public sealed class SampleActivity : CodeActivity  
{  
    public SampleActivity()  
    {  
        base.Constraints.Add(ActivityDisplayNameIsNotSetWarning());  
    }  
  
    // Activity implementation omitted.  
}  
```  
  
 <span data-ttu-id="61964-120">宿主还可使用 <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> 为工作流中的活动指定此约束，将在下一节中对此内容进行介绍。</span><span class="sxs-lookup"><span data-stu-id="61964-120">The host could also specify this constraint for activities in a workflow by using <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>, which is covered in the next section.</span></span>  
  
 <span data-ttu-id="61964-121"><xref:System.Activities.Validation.AddValidationError> 活动用于生成验证错误或警告，而无需对表达式进行计算。</span><span class="sxs-lookup"><span data-stu-id="61964-121">The <xref:System.Activities.Validation.AddValidationError> activity is used to generate a validation error or warning without requiring the evaluation of an expression.</span></span> <span data-ttu-id="61964-122">其属性类似于 <xref:System.Activities.Validation.AssertValidation> 并且可以将其与约束的流控制活动（如 <xref:System.Activities.Statements.If> 活动）结合使用。</span><span class="sxs-lookup"><span data-stu-id="61964-122">Its properties are similar to <xref:System.Activities.Validation.AssertValidation> and it can be used in conjunction with flow control activities of a constraint such as the <xref:System.Activities.Statements.If> activity.</span></span>
  
### <a name="workflow-relationship-activities"></a><span data-ttu-id="61964-123">工作流关系活动</span><span class="sxs-lookup"><span data-stu-id="61964-123">Workflow Relationship Activities</span></span>

<span data-ttu-id="61964-124">可以使用多个验证活动，这些活动提供工作流中与验证的活动有关的其他活动的相关信息。</span><span class="sxs-lookup"><span data-stu-id="61964-124">Several validation activities are available that provide information about the other activities in the workflow in relation to the activity being validated.</span></span> <span data-ttu-id="61964-125"><xref:System.Activities.Validation.GetParentChain> 返回一个活动集合，该集合包含当前活动和根活动之间的所有活动。</span><span class="sxs-lookup"><span data-stu-id="61964-125"><xref:System.Activities.Validation.GetParentChain> returns a collection of activities that contains all of the activities between the current activity and the root activity.</span></span> <span data-ttu-id="61964-126"><xref:System.Activities.Validation.GetChildSubtree> 提供一个活动集合，该集合包含采用递归模式的子活动，并且 <xref:System.Activities.Validation.GetWorkflowTree> 获取工作流中的所有活动。</span><span class="sxs-lookup"><span data-stu-id="61964-126"><xref:System.Activities.Validation.GetChildSubtree> provides a collection of activities that contains the child activities in a recursive pattern, and <xref:System.Activities.Validation.GetWorkflowTree> gets all the activities in the workflow.</span></span>  
  
<span data-ttu-id="61964-127">下面的示例定义了一个 `CreateState` 活动。</span><span class="sxs-lookup"><span data-stu-id="61964-127">In the following example, a `CreateState` activity is defined.</span></span> <span data-ttu-id="61964-128">`CreateState` 活动必须包含在 `CreateCountry` 活动中，并且 `GetParent` 方法返回一个强制此要求的约束。 </span><span class="sxs-lookup"><span data-stu-id="61964-128">The `CreateState` activity must be contained within a `CreateCountry` activity, and the `GetParent` method returns a constraint that enforces this requirement.</span></span> <span data-ttu-id="61964-129">`GetParent` 将 <xref:System.Activities.Validation.GetParentChain> 活动与 <xref:System.Activities.Statements.ForEach%601> 结合使用，以检查 `CreateState` 活动的父活动，从而确定是否满足要求。</span><span class="sxs-lookup"><span data-stu-id="61964-129">`GetParent` uses the <xref:System.Activities.Validation.GetParentChain> activity in conjunction with a <xref:System.Activities.Statements.ForEach%601> activity to inspect the parent activities of the `CreateState` activity to determine if the requirement is met.</span></span>  
  
```csharp  
public sealed class CreateState : CodeActivity  
{  
    public CreateState()  
    {  
        base.Constraints.Add(CheckParent());  
        this.Cities = new List<Activity>();              
    }  
  
    public List<Activity> Cities { get; set; }  
  
    public string Name { get; set; }    
  
    static Constraint CheckParent()  
    {  
        DelegateInArgument<CreateState> element = new DelegateInArgument<CreateState>();  
        DelegateInArgument<ValidationContext> context = new DelegateInArgument<ValidationContext>();                          
        Variable<bool> result = new Variable<bool>();  
        DelegateInArgument<Activity> parent = new DelegateInArgument<Activity>();  
  
        return new Constraint<CreateState>  
        {                                     
            Body = new ActivityAction<CreateState,ValidationContext>  
            {                      
                Argument1 = element,  
                Argument2 = context,  
                Handler = new Sequence  
                {  
                    Variables =  
                    {  
                        result   
                    },  
                    Activities =  
                    {  
                        new ForEach<Activity>  
                        {                                  
                            Values = new GetParentChain  
                            {  
                                ValidationContext = context                                      
                            },  
                            Body = new ActivityAction<Activity>  
                            {     
                                Argument = parent,   
                                Handler = new If()  
                                {                                            
                                    Condition = new InArgument<bool>((env) => object.Equals(parent.Get(env).GetType(),typeof(CreateCountry))),                                          
                                    Then = new Assign<bool>  
                                    {  
                                        Value = true,  
                                        To = result  
                                    }  
                                }  
                            }                                  
                        },  
                        new AssertValidation  
                        {  
                            Assertion = new InArgument<bool>(result),  
                            Message = new InArgument<string> ("CreateState has to be inside a CreateCountry activity"),                                                                  
                        }  
                    }  
                }  
            }  
        };  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // not needed for the sample  
    }  
}  
```
  
## <a name="additional-constraints"></a><span data-ttu-id="61964-130">其他约束</span><span class="sxs-lookup"><span data-stu-id="61964-130">Additional Constraints</span></span>  
 <span data-ttu-id="61964-131">工作流宿主创作者可以通过创建约束并将这些约束添加到 <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> 实例的 <xref:System.Activities.Validation.ValidationSettings> 字典中为工作流中的活动指定其他验证约束。</span><span class="sxs-lookup"><span data-stu-id="61964-131">Workflow host authors can specify additional validation constraints for activities in a workflow by creating constraints and adding them to the <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> dictionary of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="61964-132"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> 中的每个项目都包含应用约束的活动类型以及用于该活动类型的其他约束列表。</span><span class="sxs-lookup"><span data-stu-id="61964-132">Each item in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> contains the type of activity for which the constraints apply and a list of the additional constraints for that type of activity.</span></span> <span data-ttu-id="61964-133">为工作流调用验证时，指定类型的每个活动（包括派生的类）都计算约束。</span><span class="sxs-lookup"><span data-stu-id="61964-133">When validation is invoked for the workflow, each activity of the specified type, including derived classes, evaluates the constraints.</span></span> <span data-ttu-id="61964-134">在本示例中，将上一节中的 `ActivityDisplayNameIsNotSetWarning` 约束应用于工作流中的所有活动。</span><span class="sxs-lookup"><span data-stu-id="61964-134">In this example, the `ActivityDisplayNameIsNotSetWarning` constraint from the previous section is applied to all activities in a workflow.</span></span>  
  
```csharp  
Activity wf = new Sequence  
{  
    // Workflow Details Omitted.  
};  
  
ValidationSettings settings = new ValidationSettings()  
{  
  
    AdditionalConstraints =  
    {  
        {typeof(Activity), new List<Constraint> {ActivityDisplayNameIsNotSetWarning()}},       
    }  
};  
  
// Validate the workflow.  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
// Evaluate the results.  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error in " + error.Source.DisplayName + ": " + error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning in " + warning.Source.DisplayName + ": " + warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="61964-135">如果 <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> 的 <xref:System.Activities.Validation.ValidationSettings> 属性为 `true`，则在通过调用 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 调用验证时只计算指定的其他约束。</span><span class="sxs-lookup"><span data-stu-id="61964-135">If the <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> property of <xref:System.Activities.Validation.ValidationSettings> is `true`, then only the specified additional constraints are evaluated when validation is invoked by calling <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="61964-136">对于检查工作流的特定验证配置，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="61964-136">This can be useful for inspecting workflows for specific validation configurations.</span></span> <span data-ttu-id="61964-137">但是，请注意调用工作流时，对在工作流中配置的验证逻辑进行计算并且必须传递给该工作流才能成功开始。</span><span class="sxs-lookup"><span data-stu-id="61964-137">Note however that when the workflow is invoked, the validation logic configured in the workflow is evaluated and must pass for the workflow to successfully begin.</span></span> <span data-ttu-id="61964-138">调用验证的详细信息，请参阅[调用活动验证](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="61964-138">For more information about invoking validation, see [Invoking Activity Validation](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md).</span></span>
