# 1930s-kr-lit-subword
한국어 형태소 분석기([kiwi](https://github.com/bab2min/kiwipiepy))에서 제공하는 서브워드(subword) 학습 함수를 활용해 1930~1939년에 출간된 조선일보 문학(시/소설) 기사 데이터를 학습시킨 1930년대 한국 문학 토크나이저.

- 토크나이저 json 파일(`1930s_ko_lit_tokenizer.json`)을 활용한 토크나이징 가능.
- json 파일 활용과 관련해서는 [ModernKoreanSubword](https://github.com/ByungjunKim/ModernKoreanSubword) 참고.

```
from kiwipiepy import Kiwi
from kiwipiepy.sw_tokenizer import SwTokenizer
from kiwipiepy.sw_tokenizer import SwTokenizerConfig

kiwi = Kiwi()

# 토크나이저 설정
tokenizer = SwTokenizer('./1930s_ko_lit_tokenizer.json', kiwi=kiwi)

# 토크나이징
tokenizer.encode('肉身이흐느적흐느적하도록 疲勞했을때만 情身이 銀貨처럼 맑소')
vocab_list = tokenizer.encode('肉身이흐느적흐느적하도록 疲勞했을때만 情身이 銀貨처럼 맑소')
[tokenizer.id2vocab[i] for i in vocab_list]
```