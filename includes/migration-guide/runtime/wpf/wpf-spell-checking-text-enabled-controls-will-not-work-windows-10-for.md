### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a>支持文本的控件中的 WPF 拼写检查在 Windows 10 中将不适用于 OS 输入语言列表以外的语言

|   |   |
|---|---|
|详细信息|在 Windows 10 上运行时，拼写检查器可能不适用于支持 WPF 文本的控件，因为平台拼写检查功能仅适用于输入语言列表中的语言。在 Windows 10 中，将语言添加到可用键盘的列表时，Windows 自动下载并安装相应的按需功能 (FOD) 包，以提供拼写检查功能。 通过将语言添加到输入语言列表，将支持拼写检查器。|
|建议|请注意，必须将要进行拼写检查的语言或文本添加到输入语言以在 Windows 10 中使用拼写检查功能。|
|范围|边缘|
|版本|4.6|
|类型|运行时|

