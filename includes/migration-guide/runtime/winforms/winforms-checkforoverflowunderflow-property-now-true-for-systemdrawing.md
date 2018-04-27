### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>对于 System.Drawing，WinForm 的 CheckForOverflowUnderflow 属性现在为 true

|   |   |
|---|---|
|详细信息|System.Drawing.dll 程序集的 CheckForOverflowUnderflow 设置为 true。|
|建议|之前在发生溢出时，结果会在不提示的情况下被截断。 现在引发了 <xref:System.OverflowException?displayProperty=name> 异常。|
|范围|边缘|
|版本|4.5|
|类型|运行时|

