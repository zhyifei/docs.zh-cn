### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>在启用触摸的系统上调用 System.Windows.Input.PenContext.Disable 可能会引发 ArgumentException

|   |   |
|---|---|
|详细信息|在某些情况下，在启用触摸的系统上调用内部 <strong>System.Windows.Intput.PenContext.Disable</strong> 方法可能会因为重新进入而引发未处理的 <code>T:System.ArgumentException</code>。|
|建议|此问题已在 .NET Framework 4.7 中得到解决。 若要避免此异常，升级到 .NET Framework 4.7 及以上版本。|
|范围|边缘|
|版本|4.6.1|
|类型|重定目标|

