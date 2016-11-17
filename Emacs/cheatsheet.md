# Cheat Sheet

- `C-x C-c`                                        关闭
- `C-x k`                                          关闭 buffer

- 'C-x C-s'                                        保存

## Navigate

- 'C-a'           beginning-of-line                行首
- 'C-e'           end-of-line                      行尾

- 'M-a'           backward-sentence                句首
- 'M-e'           forward-sentence                 句尾

- 'M-{'           backward-paragraph               上一段
- 'M-}'           forward-paragraph                下一段

- 'M-<'           end-of-buffer                    文档头
- 'M->'           beginning-of-buffer              文档尾

- 'C-p'           previous-line                    上一行 
- 'C-n'           next-line                        下一行
- 'C-b'           backward-char                    上一字符
- 'C-f'           forward-char                     下一字符

- 'M-b'           backward-word                    上一单词
- 'M-f'           forward-word                     下一单词

- 'C-x ['         backward-page                    上一页
- 'C-x ]'         forward-page                     下一页

- 'C-v'           scroll-up                        下翻一页
- 'M-v'           scroll-down                      上翻一页
- 'C-l'           recenter                         当前一行置页面中间

- 'M-r'                                            移动到页面中间行首位置
- 'M-g M-g'                                        移动到指定行
- 'M-g g'         goto-line                        移动到指定行

- 'M-n'           digit-argument                   重复下个命令n次
- 'C-u n'         universal-argument               重复下个命令n次，默认为4


## Edit

- 'C-x C-f'       find-file                        打开文件
- 'C-x C-v'       find-alternate-file              打开另一个文件

- 'C-x C-s'       save-buffer                      保存文件
- 'C-x C-w'       write-file                       另存文件

- 'C-q (n)'       quoted-insert                    插入字符，n 表示字符的八进制 ASCII码
- 'C-x 8'         ucs-insert                       插入Unicode字符

- 'C-d'           delete-char                      删除光标处字符

- 'M-d'           kill-word                        删除光标起单词
- 'M-Backspace'   backward-kill-word               删除光标前单词

- 'C-k'           kill-line                        删除光标起当前行

- 'M-k'           kill-sentence                    删除光标起句子
- 'C-x Backspace' backward-kill-sentence           删除光标前句子

- '(none)'        kill-paragraph                   删除光标起段落
- '(none)'        backward-kill-paragraph          删除光标前段落

- 'C-/'           undo                             撤销
- 'C-x u'         undo                             撤销
- 'C-_'           undo                             撤销

- `C-g`           keyboard-quit                    终止当前命令

- 'C-h t'         help-with-tutorial               调出 Emacs Tutorial
- 'C-h r'         info-emacs-manual                调出 Emacs Manual
- 'C-h k'         describe-key                     查看对应 command 帮助

- 'C-o'           open-line                        插入空行
- 'C-x C-o'       delete-blank-line                删除空行
- 'C-x z'         repeat                           重复前个命令

- 'C-M-v'         scroll-other-window              向下滚动另一个窗口
- 'C-M-S-v'       scroll-other-window-down         向上滚动另一个窗口

- 'M-PageDown'    scroll-other-window              向下滚动另一个窗口
- 'M-PageUp'      scroll-other-window-down         向上滚动另一个窗口

- 'TAB'           minibuffer-complete              自动补全Minibuffer
- 'SPC'           minibuffer-complete-word         自动补全Minibuffer中一个词
- 'RET'           minibuffer-complete-and-exit     提交Minibuffer
- '?'             minibuffer-completion-help       列出所有可能补全

- `C-@`           set-mark-command                 设定标记
- 'C-x C-x'       exchange-point-and-mark          交换标记和光标位置
- 'C-w'           kill-region                      删除区域中内容
- 'C-x C-u'       upcase-region                    将区域中字母改写为大写
- 'C-x h'         mark-whole-buffer                全选
- 'C-x C-p'       mark-page                        选取一页
- 'M-h'           mark-paragraph                   选取一段
- 'M-@'           mark-word                        选取一个单词
- 'C-@ C-@'                                        加入点到标记环
- 'C-u C-@'                                        在标记环中跳跃
- 'C-x C-@'       pop-global-mark                  在全局标记环中跳跃
- '(none)'        transient-mark-mode              非持久化标记模式

- 'C-d'           delete-char                      删除光标处字符
- 'Backspace'     delete-backward-char             删除光标前字符
- 'M-\'           delete-horizontal-space          删除光标处的所有空格和Tab字符
- 'M-SPC'         just-one-space                   删除光标处的所有空格和Tab字符，但留下一个
- 'C-x C-o'       delete-blank-lines               删除光标周围的空白行，保留当前行
- 'M-^'           delete-indentation               将两行合为一行，删除之前的空白和缩进
- 'C-k'           kill-line                        从光标处起删除该行
- 'C-S-Backspace' kill-whole-line                  删除整行


- `C-a`                                            移动到行开始
- `C-@`                                            标记
- `C-n`                                            移动数行
- `C-e`                                            移动到行尾
- `C-w`                                            剪切
- `M-w`                                            复制
- `C-y`                                            粘贴

- `M-x linum-mode` 显示行号
- `M-x font-lock-mode RET` turn off syntax highlighting
- `M-x recover-file`
- 'M-x goto-char'
- 'M-x goto-line'

- `C-x o`  切换窗口
- `C-x 1`  关闭其他窗口

- `C-S-Backspace` 删除一行

## buffer

- 'C-x C-b' List all buffers
- 'C-x b'
- 'C-x k' Kill buffer