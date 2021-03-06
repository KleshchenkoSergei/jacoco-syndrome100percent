## Синдром 100%. Проверка покрытия кода в CI

Вы попали в команду максималистов, которые хотят, чтобы те авто-тесты, которые вы пишете, покрывали код на 100%.

Но вот незадача:

1. Непонятно, что такое 100%
2. Непонятно, как это сделать

Вспоминаем: покрытием кода у нас занимается JaCoCo, но он просто "сигнализирует" о том, что конкретно пошло не так.

Большинство подобных плагинов помимо целей отчётности (report) содержат ещё цель check, которая обрушает сборку, если не выполнены определённые проверки.

Что вам нужно:

1. Создать мавен-проект с тестируемым кодом из листинга кода (указан ниже по условию)
2. Изучить документацию на плагин (а конкретно на цель check)
3. Внедрить эту цель в фазу verify (обратите внимание, что эта цель итак публикуется в эту фазу)
4. Настроить правила по покрытию на 100% (при этом нужно изучить разницу между счётчиками INSTRUCTION, LINE, BRANCH, COMPLEXITY)
5. Вникнуть в тестируемый код
6. Выбрать один из счётчиков и добиться 100% покрытия через добавление новых тестов

**Важно**: использовать можно только один из следующих:

1. INSTRUCTION
2. LINE
3. BRANCH

Обратите внимание на чеклист в начале условия, он содержит подсказки по внедрению JaCoCo в ваш мавен-проект.
