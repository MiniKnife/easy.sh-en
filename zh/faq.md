## 常见问题

1. 如何在Dash中使用easy.sh？

   Dash中暂时只支持[z模式](xyz_mode.md#z模式)。

2. 如何在命令中包含$符号？

   $n会被自动识别为命令参数，如果命令中需要包含$符号，需要在$符号前添加一个\符号。
   如以下命令：
   
   ```shell
   ls -l | awk "{print $5}"
   ```

   可以使用如下命令代替：
   
   ```shell
   $ easy print-file-size 'ls -l | awk "{print \$5}"'
   ```

3. 如何在命令中包含单引号？

   在[最佳实践](best_practices.md)中建议通过单引号字符串传递命令脚本参数，如果需要在命令脚本中使用单引号，可以通过字符串拼接的方式实现，将原来的一个单引号 **`** 改为 **`\\``** 即可。
   如以下命令：
   
   ```shell
   ls -l | awk '{print $9}'
   ```
   
   可以使用如下命令代替：
   
   ```shell
   $ easy print-file-name 'ls -l | awk '\''{print $9}'\'''
   ```

4. 如何编写跨行命令？

   支持通过\符号编写跨行命令，但是会被自动合并为一行，并通过空格分隔各行内容，如以下命令：
   
   ```shell
   $ easy multi-line-echo 'echo "line1"\
   && echo "line2"'
   ```

   以上命令等同于如下命令：
   
   ```shell
   $ easy another-multi-line-echo 'echo "line1" && echo "line2"'
   ```

---