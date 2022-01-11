# 2021년, 변규홍은 어떻게 살아가고 있나요?

2021년부터, 전반적인 개발 환경과 관련된 분야에서 행했던 삽질 중 의미있는 것을 메모해 둡니다.

## 2022년 1월 2일 (일요일)

### [KoNLPy](https://github.com/konlpy/konlpy) 매인테이너

* [KoNLPy](https://github.com/konlpy/konlpy)의 0.6.0 버전 릴리즈를 요청하였고, 어느 순간 매인테이너가 되었다. Windows, Linux, Mac OS X, Arm (Non-Intel) 등 다양한 환경과 Python 2.7, Python 3.6 등 다양한 버전, 그리고 CoLab 등의 환경 모두에서 테스트를 해 보고 있다. 

## 2021년 11월 16일 (화요일)

### Inference on CPU for GPT-J

* 24GB 정도 되는 모델은 48~50GB 정도 되는 CPU 메모리를 사용하여 CPU inference 를 어느 정도는 실행할 수 있다. 이때 주의점은 bfloat16 등을 쓰거나 하도록 되어 있는 경우가 있다면 이를 적절히 해지해야 한다. 


## 2021년 11월 6일 (토요일)

### Microsoft office Click-to-run CPU 점유율

* [Link](https://answers.microsoft.com/en-us/msoffice/forum/all/microsoft-office-click-to-run-process-running-with/c88b90d6-0805-408d-a7bd-47ef8cf31f24)

## 2021년 3월 27일 (토요일)

### 첫 Translation pull request

* [어떤 공개 서한을 다국어로 번역하자는 제안](https://github.com/rms-open-letter/rms-open-letter.github.io/issues/1186)하고 이틀 뒤에 올린 [Pull Request](https://github.com/rms-open-letter/rms-open-letter.github.io/pull/2443)가 merge되었다.
* [해당 공개 서한과 정반대의 입장을 취하는 공개 서한](https://github.com/rms-support-letter/rms-support-letter.github.io)의 [한국어 번역](https://rms-support-letter.github.io/index-ko.html)을 보면서 여러 가지 고민이 든다. 단순히 내용을 어떻게 옮길 것인지뿐만 아니라 이 내용을 비판적으로 수용하기 위한 - 우리말로 된 사전 지식을 어떻게 제공해야 좋을까?

## 2021년 3월 17일 (수요일)

### LATIN CAPITAL LETTER I WITH DOT ABOVE 에서 시작된 관찰

* [UnicodeData.txt](https://www.unicode.org/Public/UCD/latest/ucd/UnicodeData.txt)에 따르면, `U+0130`(`&#0304`), `'İ'` 즉 *Latin Capital Letter I with Dot Above*을 소문자로 표현하면 평범한 i가 된다.
* 하지만 Python 3.3 및 그 이상의 버전에서는 str.lower() 를 할 때 `'i\u0307'`이 된다. (1글자 -> 2글자)
* [Python Bug Tracker - Issue 17252](https://bugs.python.org/issue17252)에서 이에 대한 흥미로운 토론을 읽을 수 있다. 
* 좀더 많은 이야기는 [Dotted and dotless I](https://en.wikipedia.org/wiki/Dotted_and_dotless_I) 혹은 [İ와_ı](https://ko.wikipedia.org/wiki/%C4%B0%EC%99%80_%C4%B1)에도 올라와 있다.
* Python 3.6.10 기준으로는 이 문자를 제외하고는 str.lower() 를 하는 것만으로 문자열의 길이가 달라지는 경우는 없다.
* 흥미롭게도 str.upper() 를 하는 것만으로 문자열의 길이가 달라지는 경우는 102 건이나 된다.

```
print([chr(y) for y in range(0x110000) if len(chr(y).upper()) != len(chr(y))])
```

## 2021년 1월 13일 (수요일)

### 현재 다니고 있는 회사의 이름 (...)

* **Skelter Labs**
* **스켈터랩스**
* 영어로 쓸 때 띄어쓰기 포함 12글자, 한글로 적을 때 띄어쓰기 없이 5글자이다.

## 2021년 1월 4일 (월요일)

### Slack 장애 Report

* Slack 에도 장애 리포트 사이트 [https://status.slack.com/](https://status.slack.com/)가 있다.
* Slack 이중화는 어떤 식으로 할 수 있을지.

## 2021년 1월 3일 (일요일)

### `github.com/[ID]/[ID]` Repository 

* `[링크](파일명)` 형식을 쓰면 `[ID]` 저장소 내의 해당 파일로 가는 링크가 Gitub 프로필에 노출된다.

## 2021년 1월 1일 (금요일)

### 구형 (2009) 컴퓨터를 포맷할 때 주의할 점들.

* USB Flash Memory 기반의 부팅을 지원하지 않는 경우가 많다.
* [iODD](iODD.md) 를 사용하더라도 경우에 따라 USB 전원 포트 출력이 부족할 수 있다.
  * Y 자형 USB 전원 보조 케이블 등을 사용하여도 사정이 그리 나아지지 않기도 한다.
* iODD 에 Windows 10 ISO 파일을 잘 심어도, 다른 파티션이 있어서 문제가 될 수 있다.
* `_ISO` 폴더에 저장된 파일이 단편화가 일어나 있을 경우 `defrag` 에러만 뜬다. 조각모음 필수.
* `C:\GPKI` 를 깔끔하게 백업한다.
* Windows 에는 즐겨찾기 백업하는 것도 잊지 않는다.
* 같은 iODD 라고 해도 안에 들어있는 SSD 유형에 따라 전력 소모량이 적은 것을 찾을 수 있다.
* Windows 10 미디어 다운로드 도구로 USB 자체를 바꾸거나, ISO 파일만 따로 받을 수도 있다.
* `말랑말랑 플랫폼` 기반으로 설치한 `한글 2020`은 `K-에듀파인`의 `ODT 패치`와 호환되지 않는다.
  * 정확히는 `ODT 패치`가 `한글 2020`을 설치되어 있는 버전으로 인정하지 않는다.
  * 이 경우엔 해당 시도교육청을 통해 내려온 `한글 2018`을 설치할 수밖에 없다.
* 동일 메인보드에 '디지털 라이선스'가 걸려 있다면 이 라이선스를 Microsoft 계정에 연동시켜 라이선스를 이전시킬 수 있다.
 
# 변규홍은 누구?

[combacsa](https://github.com/combacsa)을 참조해 주세요.
