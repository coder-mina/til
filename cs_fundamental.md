## ASCII code vs. Unicode

* 문자, 기호 등을 컴퓨터에 저장하고 사용하기 위해 부호화 혹은 문자 인코딩이 필요하다. 부호화된 문자를 복원하는 건 복호화.
* ASCII (American Standard Code for Information Interchange) - 1960년대 미국에서 정의한 표준화된 부호 체계. 7비트를 사용하며, 고로 128개의 문자/기호의 인코딩을 표현 가능. 이는 영문 키보드로 입력 가능한 모든 문자/기호를 표현할 수 있지만, 전세계 모든 언어들을 표현할 수는 없음.
* Unicode - 전세계 언어의 문자들을 정의하기 위한 국제 표준 코드. 문자 하나당 최대 4바이트. 유니코드의 인코딩 방식은 다양한데, UTF-8, UTF-16 등이 있음. 
* http://blog.naver.com/PostView.nhn?blogId=wonggss&logNo=220885836995&categoryNo=0&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView
* 문자 집합 (character set) = 표현해야 할 문자와 특수 문자를 정의하고 그 순서를 지정한 것.
* 코드화된 문자 집합 (coded character set) = 문자 집합을 행렬의 코드 형태로 표기한 것.
* 인코딩 방식 = 문자 집합을 컴퓨터에 저장하기 위해 byte 형태로 표현한 것.



## Bitwise Operation

* | (bitwise OR), ^ (bitwise XOR), ~ (bitwise NOT)