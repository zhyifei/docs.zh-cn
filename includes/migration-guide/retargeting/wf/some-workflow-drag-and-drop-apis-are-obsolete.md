### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a>某些工作流拖放 API 已过时

|   |   |
|---|---|
|详细信息|此工作流拖放 API 已过时，如果针对 4.5 重新生成应用，将引发编译器警告。|
|建议|应改用支持包含多个对象的操作的新 <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name> API。 或者，可以禁止显示生成警告，也可以使用较早的编译器避免出现此类警告。 API 仍受支持。|
|范围|次要|
|版本|4.5|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType></li></ul>|

