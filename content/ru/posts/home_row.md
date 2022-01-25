---
title: Как настроить моды домашнего ряда
description: "Как настроить Home Row в QMK"
date: 2022-01-25T12:00:00+03:00
draft: true
tags: ["qmk", "keyboard", "keymap", "перевод"]


---

{{< translate-box pretext="Статья является переводом. Оригинал от" author="precondition" url="https://precondition.github.io/home-row-mods" posttext="." >}}

{{< highlight bash>}} A bunch of code here {{< /highlight >}}

<br>



Если вы просматривали сообщества, посвященные механическим клавиатурам, и особенно нише эргономичных механических клавиатур, Вы могли встретить термин "home row mode" и задаться вопросом, что бы это могло значить. Что ж, давайте я Вам объясню!



# Что такое моды домашнего ряда?

Давайте сначала разберемся с этим термином. Под "home row" (или по-русски "домашним рядом") подразумевается средний ряд буквенных клавиш. На английской QWERTY-клавиатуре это будет <kbd>A</kbd><kbd>S</kbd><kbd>D</kbd><kbd>F</kbd><kbd>G</kbd><kbd>H</kbd><kbd>J</kbd><kbd>K</kbd><kbd>L</kbd><kbd>;</kbd>. Этот ряд называется "_домашним_", потому что, если следовать правилам печати, именно на этот ряд клавиш должны опираться ваши пальцы. Метки на <kbd>F</kbd> и <kbd>J</kbd> помогают найти исходное положение, не глядя на клавиатуру - это особенно важно для относительно больших клавиатур, на которых для нажатия некоторых клавиш, таких как <kbd>Backspace</kbd> или стрелки на классической <abbr title="Ten Key Less (клавиатуры, у которых отсутствует цифровой блок с правой стороны)">TKL</abbr>, необходимо двигать руками, что может сбить вас с исходного положения.

{{< figure src="https://hygo.com/wp-content/uploads/2017/06/f-j-5-bumps-on-keyboard.jpg" title="Метки на клавишах F и J" >}}

Далее - "моды". Что подразумевается под "модами"? В данном случае под "модами" подразумеваются модификаторы, то есть <kbd>⇧ Shift</kbd>, <kbd>⎈ Control</kbd>, <kbd>⎇ Alt</kbd> и <kbd>◆ GUI</kbd>. Последний модификатор в списке также известен как WinKey в Windows, Command в MacOS или Super/Meta[^1] в Linux и BSD. Его не следует путать с реальными графическими интерфейсами пользователя.



[^1]: "Meta" is an ambiguous modifier name. It used to be its own modifier but with the advent and domination of IBM PC-style keyboards, you won't find a physical <kbd>Meta</kbd> key anymore but the term remained in some places even as we standardised to the 2×4 modifiers of the HID spec that we know today. Sometimes, that's how some Linux apps call the Super/GUI modifier but in GNU Emacs, Meta actually refers to the Alt modifier by default, unless you remap it. Meanwhile, `xmodmap` and `xkb` map the level 2 of `<LALT>` to `Meta_L` thus meaning that Shift+Alt = Meta. The [Symbolics 3600](https://deskthority.net/download/file.php?id=47925) keyboard features both a <kbd>Super</kbd> and a <kbd>Meta</kbd> key but no <kbd>Alt</kbd>. On the [SAIL keyboard](http://xahlee.info/kbd/iold51593/sail_keyboard_8cd7f.jpg), <kbd>Meta</kbd> lives alongside <kbd>Alt</kbd> with no <kbd>Super</kbd> in sight. All in all, I'm in favour of abandoning the use of this term.