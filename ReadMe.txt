---MainActivity.cs---
Создали View DrawView, его запускаем в MainActivity, там где
//--------------------------------------
DrawView draw = new DrawView(this);
            draw.Start(); //параметры цвета, толщины, объекты для Paint, Canvas, Path

            SetContentView(draw);
//-----------------------------------

---DrawView.cs---
-Start()  - параметры цвета, толщины, объекты для Paint, Canvas, Path.

-OnSizeChanged(int w, int h, int oldw, int oldh) - определяем при запуске или изменении размера область для рисованияю

-OnDraw(Canvas canvas) - переопределяем OnDraw, где мы рисуем битмап всего рисунка и отрисовываем текущий путь, 
который еще не закончился.

-OnTouchEvent (MotionEvent e) - получаем точки нашего тача, и дальше по нажатию (MotionEventActions.Down) 
перемещаем начало пути на коррдинаты нашего нажатия, при движении (MotionEventActions.Move) проводим линию 
к новым координатам нашего нажатия, когда отпускаем (MotionEventActions.Up) - отрисовываем то, 
что провели и текщий путь очищаем. 

По Invalidate перересовываем экран.