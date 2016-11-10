# 格式检查

如果 Java 虚拟机准备加载（ §5.3）某个预期为 Class 文件格式的文件，它首先应保证这个文件符合 Class 文件格式（ §4.1）的基本格式标准，这个过程就被称为格式检查。 格式检查需要确认 Class 文件的开头 4 个字节必须为正确的魔数，所有预定义的属性必须符合它们应有的长度，文件的尾部不能缺少或者多出额外的字节，常量池必须不含任何被规范未预定义的信息。
这个基本的 Class 文件完整性检查对于 Class 文件的内容的后续解析工作是非常有必要的。格式检查本应独立于字节码验证，它们两者都是都是 Class 文件验证过程的一部分。但由于历史原因，格式检查与字节码验证曾经混淆在一起，因为它们两者都是完整性检查的一种形式。 