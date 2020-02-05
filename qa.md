## Question & Answer

1. How to use easy.sh in Dash?

   Only [z mode](xyz_mode.md#z-mode) is currently supported in Dash.

2. How do I include the $ sign in a command?

   `$n` will be automatically recognized as a command parameter. If the command needs to include the `$` sign, you need to add a `\` sign before the `$` sign.
   
   As the following command:
   
   ```shell
   ls -l | awk "{print $5}"
   ```

   You can use the following command instead:
   
   ```shell
   $ easy print-file-size 'ls -l | awk "{print \$5}"'
   ```

3. How do I include single quotes in a command?

   In the [best practice](best_practices.md), it is recommended to pass command script parameters through single quoted strings. If you need to use single quotes in the command script, you can use string concatenation to change the original single quote **`** to **`\\``**.

   As the following command:
   
   ```shell
   ls -l | awk '{print $9}'
   ```
   
   You can use the following command instead:
   
   ```shell
   $ easy print-file-name 'ls -l | awk '\''{print $9}'\'''
   ```

4. How to write cross-line commands?

   Support for writing cross-line commands through the `\` symbol, but they are automatically merged into one line, and each line is separated by a space, such as the following command:
   
   ```shell
   $ easy multi-line-echo 'echo "line1"\
   && echo "line2"'
   ```

   The above command is equivalent to the following command:
   
   ```shell
   $ easy another-multi-line-echo 'echo "line1" && echo "line2"'
   ```

---