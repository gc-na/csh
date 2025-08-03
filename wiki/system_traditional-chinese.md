<!--
Meta Description: # 在 C 語言中的 system 函數：使用、範例與注意事項 ## 摘要 `system` 函數是 C 語言標準庫中的一個函數，用於執行操作系統命令，並在程序中獲取其返回狀態。 ## 文檔 ### 目的 `system` 函數的主要目的是允許 C 程序通過向操作系統發送命令來執行外部指令。它可以用...
Meta Keywords: system, return_value, include, int, command
-->

# 在 C 語言中的 system 函數：使用、範例與注意事項

## 摘要
`system` 函數是 C 語言標準庫中的一個函數，用於執行操作系統命令，並在程序中獲取其返回狀態。

## 文檔
### 目的
`system` 函數的主要目的是允許 C 程序通過向操作系統發送命令來執行外部指令。它可以用來運行如 shell 命令、批處理文件等，並返回執行結果。

### 語法
```c
#include <stdlib.h>

int system(const char *command);
```

### 使用方法
- `command`：一個指向以 null 結尾的字元串，表示要執行的命令。
- 返回值：如果成功執行命令，返回命令的退出狀態；如果發生錯誤，返回 -1。

### 詳細說明
`system` 函數會創建一個子進程來執行指定的命令。在執行期間，該程序會暫停，直到子進程完成。這使得 `system` 函數適合用於需要與操作系統進行交互的情況，例如執行腳本、啟動應用程序等。

## 範例
以下是 `system` 函數的基本使用範例：

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int return_value;
    
    // 執行 ls 命令（在 UNIX/Linux 系統中）
    return_value = system("ls -l");
    
    if (return_value == -1) {
        perror("system call failed");
    } else {
        printf("Command executed successfully with return value: %d\n", return_value);
    }
    
    return 0;
}
```

## 解釋
- **常見陷阱**：
  - `system` 函數的執行依賴於操作系統的 shell，因此在不同平台上可能會產生不同的行為。
  - 在使用 `system` 函數時，要注意命令的安全性，特別是來自用戶輸入的命令，可能會導致安全風險，如命令注入。
  
- **替代方案**：
  - 對於需要更高控制或安全的情況，建議使用 `fork` 和 `exec` 系列函數來創建子進程並執行命令。

## 一句總結
`system` 函數使 C 程序能夠方便地執行操作系統命令，但需謹慎使用以避免安全漏洞。