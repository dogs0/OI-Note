## fopen
fopen是C语言的文件IO  
属于头文件`cstdio`  

### 方法
1. 打开文件:  `FILE* fopen(const char* filename, const char* mode);`
2. 写入:      `int fprintf(FILE* stream, const char* fotmat, ...);`
3. 读出:      `int fscanf(FILE* stream, const char* format, ...);`
4. 刷新缓冲   `int fflush(FILE* stream);`
5. 关闭       `int fclose(FILE* stream);`

对于方法(1)的mode参数,有以下合法值
|名称|用途|
|---|---|
|r|Read   读|
|w|Write  写|
|a|Append 加|
|+|   可读写|
|b|Bin二进制|

