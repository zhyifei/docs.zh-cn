### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>Page.LoadComplete 事件不再导致 System.Web.UI.WebControls.EntityDataSource 控件调用数据绑定

|   |   |
|---|---|
|详细信息|<xref:System.Web.UI.Page.LoadComplete> 事件不再导致 <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=name> 控件针对 create/update/delete 参数的更改来调用数据绑定。 此更改消除到数据库的外来行程，防止重置控件的值，并生成与其他数据控件一致的行为，例如 <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=name> 和 <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=name>。 在应用程序依赖于在 <xref:System.Web.UI.Page.LoadComplete> 事件中调用数据绑定的极少数情况下，此更改会产生不同的行为。|
|建议|如果需要数据绑定，请在回发之前的事件中手动调用数据绑定。|
|范围|边缘|
|版本|4.5|
|类型|运行时|

