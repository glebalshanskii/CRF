# Введение в Condotional Random Fields (CRF)

from [Introduction to Conditional Random Fields](http://blog.echen.me/2012/01/03/introduction-to-conditional-random-fields/)

Представьте, что у вас есть последовательность снимков дня жизни Джастина Бибера, и вы хотите пометить каждый снимок названием действия, которое происходит на нем (еда, сон, вождение и т.д.). Как вы можете это сделать?

Один из путей - игнорировать тот факт, что снимки представляют собой последовательность, и строить классификатор для кадого снимка. К примеру, взяв множество снятых за месяц помеченных снимков, вы можете выучить, что темные снимки, снятые в 6 утра, чаще всего про сон, снимки с множеством ярких цетов скорее всего про танцы, снимки с машиной - про вождение, и так далее.

При игнорировании того аспекта, что снимки представляют собой последовательность, вы теряете множество информации. Например, что присходит, когда вы видите близко снятое изображение рта - это про пение или про еду? Если вы знаете, что предыдущее изобраение - это изображение едящего или готовящего Джастина Бибера, то более вероятно, что это изображение рта про еду; если, однако, предыдущее изображние содержит поющего или танцующего Джастина Бибера, то и это изображение вероятнее всего про пение.

Таким образом,  чтобы увеличить точность нашего алгоритма разметки, мы также рассматривать метки соседних изобраений, и это в точности то, что делают **conditional random fields**.

