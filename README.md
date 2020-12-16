# 搭建流水账.

## 使用 EditorConfig 作为跨编辑统一代码风格

### EditorConfig 是什么

EditorConfig 可以帮助开发者在不同的编辑器和IDE之间定义和维护一致的代码风格.

```ini
root = true
[*]
; 字符集使用utf-8
charset = utf-8
; Unix风格的换行符, 
end_of_line = lf
; 每个文件以换行符结束.
insert_final_newline = true
; 缩进使用空格
indent_style = space
; 缩进长度为2个空格
indent_size = 2
; 一行最多100个字符
max_line_length = 100
```

### EditorConfig 格式

EditorConfig 使用的是 `INI 格式`, 目的是可以与 `Python ConfigParser Library` 兼容,  `;` 或者 `#` 作为注释。注释应该独占一行.
EditorConfig 文件使用 `UTF-8格式`、`CRLF` 或者 `LF` 作为换行符.

### 支持的属性

注意：不是每种属性所有的编辑器或IDE都支持, 详情请查看 [Wiki](https://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties).

- `indent_style`: 设置缩进风格 支持 `tab` 和 `space`, 其中 `tab` 为 `hard-tabs`, `space` 为 `soft-tabs`.
- `indent_size`: 设置整数表示规定每级缩进的列数和 `soft-tabs` 的空格数, 如果 `indent_style` 为 `tab` , 如果已经设置 `tab_width` 值的话,则会使用 `tab_width`的值.
- `tab_width`: 设置整数用于指定 `tab` 代表的空格数, 默认值与 `indent_size` 的值一致, 通常无需设置该值.
- `end_of_line`: 设置换行符格式, 支持的有 `lf`（Unix风格）、`cr`（Mac风格）、`crlf`（Windows风格）.
- `charset`: 设置字符集.  支持 `latin1`、`utf-8`、`utf-8-bom`、`utf-16be` 和 `utf-16le`, 通常使用 `utf-8` .
- `trim_trailing_whitespace`: 设置为 `true` 则表示会去除换行行首的任意空白字符, `false` 反之.
- `insert_final_newline`: 设置为 `true` 则表示文件会以一个空白行结尾, `false` 反之.
- `roor`: 表示是最顶层的配置文件, 为 `true` 时才会停止查找 `.editorconfig` 文件.

目前所有的属性名和属性值是不区分大小写的，在编译时会将其都转成小写。通常如果没有明确指定某个属性时，则会使用编辑器默认的配置。

推荐在某些情况下不要指定一些属性。比如：

- 当 `tab_width` 与 `indent_size` 相同时则不需要特别指定.
- 当 `indent_style` 为 `tab` 时不需要特别指定 `indent_size`.

### 插件下载

目前 `EditorConfig` 已经支持了所有主流的编辑器及ide, 前往[官网](https://editorconfig.org/#download) 进行下载. 或者直接在各自ide中的插件市场直接下载.
