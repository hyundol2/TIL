## pprint

> Pretty Print의 약자로 딕셔너리 자료형을 예쁘게 출력하고 싶다면,,, 사용해보자
> 

```json
// ex.json

{
    "adult": false,
    "backdrop_path": "/tXHpvlr5F7gV5DwgS7M5HBrUi2C.jpg",
    "genre_ids": [
        18,
        80
    ],
    "id": 278,
    "original_language": "en",
    "original_title": "The Shawshank Redemption",
    "overview": "촉망받는 은행 간부 앤디 듀프레인은 아내와 그녀의 정부를 살해했다는 누명을 쓴다. 주변의 증언과 살해 현장의 그럴듯한 증거들로 그는 종신형을 선고받고 악질범들만 수용한다는 지옥같은 교도소 쇼생크로 향한다. 인간 말종 쓰레기들만 모인 그곳에서 그는 이루 말할 수 없는 억압과 짐승보다 못한 취급을 당한다. 그러던 어느 날, 간수의 세금을 면제받게 해 준 덕분에 그는 일약 교도소의 비공식 회계사로 일하게 된다. 그 와중에 교도소 소장은 죄수들을 이리저리 부리면서 검은 돈을 긁어 모으고 앤디는 이 돈을 세탁하여 불려주면서 그의 돈을 관리하는데...",
    "popularity": 67.931,
    "poster_path": "/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg",
    "release_date": "1995-01-28",
    "title": "쇼생크 탈출",
    "video": false,
    "vote_average": 8.7,
    "vote_count": 18040
}
```

이러한 json 파일을 파이썬으로 읽어와 작업을 할때 터미널에서 보기 위해 출력해보면 

.

.

.

```python
import json

ex_json = open("ex.json", encoding="UTF8")
ex = json.load(ex_json)

print(ex)

#출력 결과
'''
{'adult': False, 'backdrop_path': '/tXHpvlr5F7gV5DwgS7M5HBrUi2C.jpg', 'genre_ids': [18, 80], 'id': 278, 'original_language': 'en', 'original_title': 'The Shawshank Redemption', 'overview': '촉망받는 은행 간부 앤디 듀프레인은 아내와 그
녀의 정부를 살해했다는 누명을 쓴다. 주변의 증언과 살해 현장의 그럴듯한 증거들로 그는 종신형을 선고받고 악질범들만 수용한다는 지옥같은
 교도소 쇼생크로 향한다. 인간 말종 쓰레기들만 모인 그곳에서 그는 이루 말할 수 없는 억압과 짐승보다 못한 취급을 당한다. 그러던 어느 날
, 간수의 세금을 면제받게 해 준 덕분에 그는 일약 교도소의 비공식 회계사로 일하게 된다. 그 와중에 교도소 소장은 죄수들을 이리저리 부리 
면서 검은 돈을 긁어 모으고 앤디는 이 돈을 세탁하여 불려주면서 그의 돈을 관리하는데...', 'popularity': 67.931, 'poster_path': '/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg', 'release_date': '1995-01-28', 'title': '쇼생크 탈출', 'video': False, 'vote_average': 8.7, 'vote_count': 
18040}
'''
```

보기가 싫다.

이때 필요한 것이 `pprint()` 함수다.

```python
import json
from pprint import pprint

ex_json = open("ex.json", encoding="UTF8")
ex = json.load(ex_json)

pprint(ex)

#출력 결과
'''
{'adult': False,
 'backdrop_path': '/tXHpvlr5F7gV5DwgS7M5HBrUi2C.jpg',
 'genre_ids': [18, 80],
 'id': 278,
 'original_language': 'en',
 'original_title': 'The Shawshank Redemption',
 'overview': '촉망받는 은행 간부 앤디 듀프레인은 아내와 그녀의 정부를 살해했다는 누명을 쓴다. 주변의 증언과 살해 현장의 '
             '그럴듯한 증거들로 그는 종신형을 선고받고 악질범들만 수용한다는 지옥같은 교도소 쇼생크로 향한다. 인간 말종 '
             '쓰레기들만 모인 그곳에서 그는 이루 말할 수 없는 억압과 짐승보다 못한 취급을 당한다. 그러던 어느 날, 간수의 '
             '세금을 면제받게 해 준 덕분에 그는 일약 교도소의 비공식 회계사로 일하게 된다. 그 와중에 교도소 소장은 죄수들을 '        
             '이리저리 부리면서 검은 돈을 긁어 모으고 앤디는 이 돈을 세탁하여 불려주면서 그의 돈을 관리하는데...',
 'popularity': 67.931,
 'poster_path': '/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg',
 'release_date': '1995-01-28',
 'title': '쇼생크 탈출',
 'video': False,
 'vote_average': 8.7,
 'vote_count': 18040}
'''
#엄청나게 편안해진 모습
```

 

특별한 기능은 없고 예쁘게 출력해주는 함수이니 딕셔너리의 변경값을 그때그때 확인하고 싶을 때 사용하면 좋을 것 같다

### pprint 출력 옵션

> 사용자의 취향에 따라 사용할 수 있는 여러 기능들도 존재한다.
> 

#### indent (들여쓰기)

- 들여쓰기 간격을 조정할 수 있다. 기본값은 1이다.

```python
pprint(ex, indent=4)

#출력 결과
'''
{   'adult': False,
    'backdrop_path': '/tXHpvlr5F7gV5DwgS7M5HBrUi2C.jpg',
    'genre_ids': [18, 80],
    'id': 278,
    'original_language': 'en',
    'original_title': 'The Shawshank Redemption',
    'overview': '촉망받는 은행 간부 앤디 듀프레인은 아내와 그녀의 정부를 살해했다는 누명을 쓴다. 주변의 증언과 살해 현장의 '
                '그럴듯한 증거들로 그는 종신형을 선고받고 악질범들만 수용한다는 지옥같은 교도소 쇼생크로 향한다. 인간 말종 '
                '쓰레기들만 모인 그곳에서 그는 이루 말할 수 없는 억압과 짐승보다 못한 취급을 당한다. 그러던 어느 날, '
                '간수의 세금을 면제받게 해 준 덕분에 그는 일약 교도소의 비공식 회계사로 일하게 된다. 그 와중에 교도소 '
                '소장은 죄수들을 이리저리 부리면서 검은 돈을 긁어 모으고 앤디는 이 돈을 세탁하여 불려주면서 그의 돈을 '
                '관리하는데...',
    'popularity': 67.931,
    'poster_path': '/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg',
    'release_date': '1995-01-28',
    'title': '쇼생크 탈출',
    'video': False,
    'vote_average': 8.7,
    'vote_count': 18040}
'''

```

#### width (줄 길이 제한) 

- 한 줄에 출력할 최대 길이를 제한하는 옵션이다. 기본값은 80이다.

```python
pprint(ex, width=400)

#출력 결과
'''
{'adult': False,
 'backdrop_path': '/tXHpvlr5F7gV5DwgS7M5HBrUi2C.jpg',
 'genre_ids': [18, 80],
 'id': 278,
 'original_language': 'en',
 'original_title': 'The Shawshank Redemption',
 'overview': '촉망받는 은행 간부 앤디 듀프레인은 아내와 그녀의 정부를 살해했다는 누명을 쓴다. 주변의 증언과 살해 현장의 그럴듯한 증거
들로 그는 종신형을 선고받고 악질범들만 수용한다는 지옥같은 교도소 쇼생크로 향한다. 인간 말종 쓰레기들만 모인 그곳에서 그는 이루 말할 
수 없는 억압과 짐승보다 못한 취급을 당한다. 그러던 어느 날, 간수의 세금을 면제받게 해 준 덕분에 그는 일약 교도소의 비공식 회계사로 일
하게 된다. 그 와중에 교도소 소장은 죄수들을 이리저리 부리면서 검은 돈을 긁어 모으고 앤디는 이 돈을 세탁하여 불려주면서 그의 돈을 관리
하는데...',
 'popularity': 67.931,
 'poster_path': '/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg',
 'release_date': '1995-01-28',
 'title': '쇼생크 탈출',
 'video': False,
 'vote_average': 8.7,
 'vote_count': 18040}
'''
```

#### sort_dicts (딕셔너리 키 정렬)

- pprint는 딕셔너리를 키값에 따라 자동 정렬해주는 게 기본값이다. 이를 방지하려면 `sort_dicts = Flase`를 사용해보자.

```python
pprint(ex, sort_dicts=False)

#출력 결과
'''
{'adult': False,
 'backdrop_path': '/tXHpvlr5F7gV5DwgS7M5HBrUi2C.jpg',
 'genre_ids': [18, 80],
 'id': 278,
 'original_language': 'en',
 'original_title': 'The Shawshank Redemption',
 'overview': '촉망받는 은행 간부 앤디 듀프레인은 아내와 그녀의 정부를 살해했다는 누명을 쓴다. 주변의 증언과 살해 현장의 '
             '그럴듯한 증거들로 그는 종신형을 선고받고 악질범들만 수용한다는 지옥같은 교도소 쇼생크로 향한다. 인간 말종 '
             '쓰레기들만 모인 그곳에서 그는 이루 말할 수 없는 억압과 짐승보다 못한 취급을 당한다. 그러던 어느 날, 간수의 '
             '세금을 면제받게 해 준 덕분에 그는 일약 교도소의 비공식 회계사로 일하게 된다. 그 와중에 교도소 소장은 죄수들을 '        
             '이리저리 부리면서 검은 돈을 긁어 모으고 앤디는 이 돈을 세탁하여 불려주면서 그의 돈을 관리하는데...',
 'popularity': 67.931,
 'poster_path': '/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg',
 'release_date': '1995-01-28',
 'title': '쇼생크 탈출',
 'video': False,
 'vote_average': 8.7,
 'vote_count': 18040}
'''
```

json 형식의 보기 힘든 데이터를 출력할 때에는 pprint를 잘 사용해보자!

### 번외

> 단순히 더 예쁘게 출력해보고 싶어서 좀 더 찾아봤다. 여기부터는 그저 예쁜 출력만을 위한 것이니 참고만 할 것!
> 

#### `json.dumps()`

- load() 함수를 사용해 json 데이터를 dictionary / list 객체로 불러왔다면 이를 다시 JSON 문자열로 변환하는 함수이다.
    - `dumps()`가 아니라 `dump()`로 사용하게 되면 TypeError가 발생하니 주의!

```python
print(json.dumps(ex))

#출력 결과
('{"adult": false, "backdrop_path": "/tXHpvlr5F7gV5DwgS7M5HBrUi2C.jpg", '
 '"genre_ids": [18, 80], "id": 278, "original_language": "en", '
 '"original_title": "The Shawshank Redemption", "overview": '
 '"\\ucd09\\ub9dd\\ubc1b\\ub294 \\uc740\\ud589 \\uac04\\ubd80 \\uc564\\ub514 '
 '\\ub4c0\\ud504\\ub808\\uc778\\uc740 \\uc544\\ub0b4\\uc640 '
 '\\uadf8\\ub140\\uc758 \\uc815\\ubd80\\ub97c '
 '\\uc0b4\\ud574\\ud588\\ub2e4\\ub294 \\ub204\\uba85\\uc744 \\uc4f4\\ub2e4. '
 '\\uc8fc\\ubcc0\\uc758 \\uc99d\\uc5b8\\uacfc \\uc0b4\\ud574 '
 '\\ud604\\uc7a5\\uc758 \\uadf8\\ub7f4\\ub4ef\\ud55c '
 '\\uc99d\\uac70\\ub4e4\\ub85c \\uadf8\\ub294 \\uc885\\uc2e0\\ud615\\uc744 '
 '\\uc120\\uace0\\ubc1b\\uace0 \\uc545\\uc9c8\\ubc94\\ub4e4\\ub9cc '
 '\\uc218\\uc6a9\\ud55c\\ub2e4\\ub294 \\uc9c0\\uc625\\uac19\\uc740 '
 '\\uad50\\ub3c4\\uc18c \\uc1fc\\uc0dd\\ud06c\\ub85c \\ud5a5\\ud55c\\ub2e4. '
 '\\uc778\\uac04 \\ub9d0\\uc885 \\uc4f0\\ub808\\uae30\\ub4e4\\ub9cc '
 '\\ubaa8\\uc778 \\uadf8\\uacf3\\uc5d0\\uc11c \\uadf8\\ub294 \\uc774\\ub8e8 '
 '\\ub9d0\\ud560 \\uc218 \\uc5c6\\ub294 \\uc5b5\\uc555\\uacfc '
 '\\uc9d0\\uc2b9\\ubcf4\\ub2e4 \\ubabb\\ud55c \\ucde8\\uae09\\uc744 '
 '\\ub2f9\\ud55c\\ub2e4. \\uadf8\\ub7ec\\ub358 \\uc5b4\\ub290 \\ub0a0, '
 '\\uac04\\uc218\\uc758 \\uc138\\uae08\\uc744 \\uba74\\uc81c\\ubc1b\\uac8c '
 '\\ud574 \\uc900 \\ub355\\ubd84\\uc5d0 \\uadf8\\ub294 \\uc77c\\uc57d '
 '\\uad50\\ub3c4\\uc18c\\uc758 \\ube44\\uacf5\\uc2dd '
 '\\ud68c\\uacc4\\uc0ac\\ub85c \\uc77c\\ud558\\uac8c \\ub41c\\ub2e4. \\uadf8 '
 '\\uc640\\uc911\\uc5d0 \\uad50\\ub3c4\\uc18c \\uc18c\\uc7a5\\uc740 '
 '\\uc8c4\\uc218\\ub4e4\\uc744 \\uc774\\ub9ac\\uc800\\ub9ac '
 '\\ubd80\\ub9ac\\uba74\\uc11c \\uac80\\uc740 \\ub3c8\\uc744 \\uae01\\uc5b4 '
 '\\ubaa8\\uc73c\\uace0 \\uc564\\ub514\\ub294 \\uc774 \\ub3c8\\uc744 '
 '\\uc138\\ud0c1\\ud558\\uc5ec \\ubd88\\ub824\\uc8fc\\uba74\\uc11c '
 '\\uadf8\\uc758 \\ub3c8\\uc744 \\uad00\\ub9ac\\ud558\\ub294\\ub370...", '
 '"popularity": 67.931, "poster_path": "/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg", '
 '"release_date": "1995-01-28", "title": "\\uc1fc\\uc0dd\\ud06c '
 '\\ud0c8\\ucd9c", "video": false, "vote_average": 8.7, "vote_count": 18040}')
```

들여쓰기도 안 돼있고, 한글도 모두 유니코드로 표현되는 모습.. 간단하게 해결할 수 있다.

`json.dumps()`의 파라미터 중 indent로 들여쓰기를 조절, ensure_ascii로 한글도 정상적으로 표현할 수 있다!

```python
print(json.dumps(ex, indent=4, ensure_ascii=False))

# 출력 결과
'''
{
    "adult": false,
    "backdrop_path": "/tXHpvlr5F7gV5DwgS7M5HBrUi2C.jpg",
    "genre_ids": [
        18,
        80
    ],
    "id": 278,
    "original_language": "en",
    "original_title": "The Shawshank Redemption",
    "overview": "촉망받는 은행 간부 앤디 듀프레인은 아내와 그녀의 정부를 살해했다는 누명을 쓴다. 주변의 증언과 살해 현장의 그럴듯한 증 
거들로 그는 종신형을 선고받고 악질범들만 수용한다는 지옥같은 교도소 쇼생크로 향한다. 인간 말종 쓰레기들만 모인 그곳에서 그는 이루 말할 
수 없는 억압과 짐승보다 못한 취급을 당한다. 그러던 어느 날, 간수의 세금을 면제받게 해 준 덕분에 그는 일약 교도소의 비공식 회계사로 일하
게 된다. 그 와중에 교도소 소장은 죄수들을 이리저리 부리면서 검은 돈을 긁어 모으고 앤디는 이 돈을 세탁하여 불려주면서 그의 돈을 관리하는
데...",
    "popularity": 67.931,
    "poster_path": "/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg",
    "release_date": "1995-01-28",
    "title": "쇼생크 탈출",
    "video": false,
    "vote_average": 8.7,
    "vote_count": 18040
}
'''
```

미세하지만 아주 조금 가독성이 좋아졌다 ㅎㅎ