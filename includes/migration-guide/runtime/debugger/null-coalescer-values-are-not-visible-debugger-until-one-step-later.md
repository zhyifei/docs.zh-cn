### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>在执行后一个步骤时才能在调试器中看到空联合器值

|   |   |
|---|---|
|详细信息|在 64 位版本的 Framework 上运行时，.NET Framework 4.5 中的 bug 导致在执行分配操作后无法立即在调试器中看到通过空联合操作设置的值。|
|建议|在调试器中多单步执行一次将正确更新本地/字段的值。 另外，此问题已在 .NET Framework 4.6 中解决；因此升级到该版本的 Framework 即可解决该问题。|
|范围|边缘|
|版本|4.5|
|类型|运行时|

