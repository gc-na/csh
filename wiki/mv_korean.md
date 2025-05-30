# [리눅스] C Shell (csh) mv 사용법: 파일 및 디렉토리 이동 및 이름 변경

## 개요
`mv` 명령어는 파일이나 디렉토리를 이동하거나 이름을 변경하는 데 사용됩니다. 이 명령어는 주로 파일 시스템 내에서 파일의 위치를 변경하거나, 파일의 이름을 새롭게 지정할 때 유용합니다.

## 사용법
기본 구문은 다음과 같습니다:
```
mv [옵션] [인수]
```

## 일반 옵션
- `-i`: 덮어쓰기 전에 사용자에게 확인을 요청합니다.
- `-f`: 강제로 덮어쓰기를 수행합니다. 사용자 확인 없이 파일을 덮어씁니다.
- `-u`: 소스 파일이 대상 파일보다 새롭거나 대상 파일이 존재하지 않을 경우에만 이동합니다.

## 일반 예제
1. 파일 이동:
   ```bash
   mv file.txt /path/to/destination/
   ```

2. 파일 이름 변경:
   ```bash
   mv oldname.txt newname.txt
   ```

3. 디렉토리 이동:
   ```bash
   mv /path/to/source_directory/ /path/to/destination_directory/
   ```

4. 사용자 확인 후 덮어쓰기:
   ```bash
   mv -i file.txt /path/to/destination/
   ```

5. 강제로 덮어쓰기:
   ```bash
   mv -f file.txt /path/to/destination/
   ```

## 팁
- 파일을 이동하기 전에 항상 현재 작업 디렉토리를 확인하세요.
- 중요한 파일을 덮어쓰기 전에 `-i` 옵션을 사용하는 것이 좋습니다.
- 여러 파일을 한 번에 이동하려면 공백으로 구분하여 파일 목록을 나열할 수 있습니다.