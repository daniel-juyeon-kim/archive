# [WARNING]: Console output during zsh initialization detected

터미널을 사용하여 작업하는 도중 이런 메세지가 나왔다.

```shell
[WARNING]: Console output during zsh initialization detected.

When using Powerlevel10k with instant prompt, console output during zsh
initialization may indicate issues.

You can:

  - Recommended: Change ~/.zshrc so that it does not perform console I/O
    after the instant prompt preamble. See the link below for details.

    * You will not see this error message again.
    * Zsh will start quickly and prompt will update smoothly.

  - Suppress this warning either by running p10k configure or by manually
    defining the following parameter:

      typeset -g POWERLEVEL9K_INSTANT_PROMPT=quiet

    * You will not see this error message again.
    * Zsh will start quickly but prompt will jump down after initialization.

  - Disable instant prompt either by running p10k configure or by manually
    defining the following parameter:

      typeset -g POWERLEVEL9K_INSTANT_PROMPT=off

    * You will not see this error message again.
    * Zsh will start slowly.

  - Do nothing.

    * You will see this error message every time you start zsh.
    * Zsh will start quickly but prompt will jump down after initialization.

For details, see:
https://github.com/romkatv/powerlevel10k/blob/master/README.md#instant-prompt

-- console output produced during zsh initialization follows --
```

요약하면 Powerlevel10k를 instant 프롬프트와 같이 사용할 때 zsh 초기화 과정에서 콘솔 출력이 발생했다.

`~/.p10k.zsh`의 설정을 변경하거나 p10k configure 명령어를 통해 설정해야 한다.

> 메세지의 큰 부분만 훑어보고 .zshrc파일만 수정해주면 되겠다라고 생각해서 많이 돌아왔다.
