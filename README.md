var counter = 0;
function start(){
    square(getWidth(), getHeight(), 5, 5, Color.green);
    setTimer(bloom, 20);
   
}

function bloom(){
    flower(Randomizer.nextInt(10, 100), Randomizer.nextInt(10, getHeight()),
    Randomizer.nextColor()); 
    if(counter >= 200){
        stopTimer(bloom);
    
   
    }
}
function flower(x, y, petalColor){
    var size = Randomizer.nextInt(10,100); 
    counter++;
    var x = Randomizer.nextInt(50,200);
    var y = Randomizer.nextInt(50, 250);
    drawCircle(size, x+18, y-11, petalColor);
    drawCircle(size, x+18, y+24, petalColor);
    drawCircle(size, x-18, y+13, petalColor);
    drawCircle(size, x+ 18, y-20, petalColor);
    drawCircle(size, x-18, y-15, petalColor);
    drawCircle(size, x-18, y-15, petalColor);
     drawCircle(size, x, y, Color.blue);


  }


function drawCircle(radius, x , y , color){
    var circle1= new Circle(25);
    circle1.setPosition(x, y);
    circle1.setColor(color);
    add(circle1);
}

function square(length, width, x, y, color){
    var grass= new Rectangle(length, width);
    grass.setPosition(x, y);
    grass.setColor(color);
    add(grass);
}