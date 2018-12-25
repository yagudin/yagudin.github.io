---
title: "Indignation Bot: дилемма заключённого с открытым кодом"
date: 2016-12-14
type: "post"
---

_Впервые опублкованно во_ [ВКонтакте](https://vk.com/misha.yagudin?w=wall94844036_272).

Разнообразные формы [дилеммы](ru.wikipedia.org/wiki/Дилемма_заключённого) [заключённого](lesswrong.com/lw/tn/the_true_prisoners_dilemma/) используют для исследования принятия решений. Интересная версия исследуется в статье [Machine Intelligence Research Institute](https://arxiv.org/abs/1401.5577): игроки — компьютерные программы, имеющие доступ к коду друг друга, и формулирующие утверждения модальной логики вида «всегда сотрудничай» (CooperateBot) или «если доказуемо, что оппонент со мной скооперируется, то кооперируйся» (FairBot).

```
def FairBot(Opponent):
　search for a proof that Opponent(FairBot) = Cooperate
　if found:
　　return Cooperate
　else:
　　return Defect
```

В статье показано, что FairBot и более сложный PrudentBot имеют некоторые хорошие характеристики, например, не кооперируются с теми, кто их предаст; кооперируются со своими копиями.

[A. Critch](acritch.com/indignationbot-1/) в своём блоге привёл забавный пример IndignationBot (сокращённо IB).

```
def IB(Opp):
　search for a proof that
　　(IB(Opp) = C) → (Opp(IB) = D)
　if found:
　　feel a sense of righteous indignation
　　return D
　else:
　　return C
```

То же самое словами: IndignationBot готов с вами скооперироваться, но если он докажет «если я буду с вами сотрудничать, то вы меня предадите» — то возмущённый откажется от кооперации.

Как поведёт себя IndignationBot встретившись с CooperatBot? Оказывается (с помощью теоремы Лёба) можно доказать, что IndignationBot эквивалентен DefectBot, который всегда предаёт. Это неожиданно и удивительно. Но, конечно, это рассуждение не позволяет делать выводов о людях, ведущих себя схожим образом: наши возможности разбираться в психологии и мотивах других не сравнимы с модальной логикой агентов.