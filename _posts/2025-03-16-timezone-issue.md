---
title: 지킬 timezone
categories: journal
---

지킬 `_config.yml`에 

```yaml
timezone: "Asia/Seoul"
future: true #옵션
```

을 포함시키고, `.gitpub/workflows/jekyll.yml` 파일에

```yaml
jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    env:
      TZ: Asia/Seoul
```

을 포함시키지 않으면, 시차 문제 때문에 시간이 맞지 않아 발행이 되지 않는 경우가 생길 수 있다. `future: true` 옵션을 주면, 제 시간이 되어서 다시 발행할(push할) 필요가 없다 (고 깃헙 코파일럿은 말한다). 이걸 포함시키니 제대로 보인다. 왜 지금까지는 그런 일이 없었지? 흥미롭네. 깃헙의 기본 시간대는 어떻게 설정되어 있을까?

```yaml
date_format: "%Y-%m-%d %H:%M:%S %z"
```

이것도 옵션이라는데, 지금으로서는 필요 없을 듯...