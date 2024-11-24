# Blockboy
tutorial
/*
    - A good starting point for new projects
*/

'use strict';

    const levelSize = vec2(20,20);

///////////////////////////////////////////////////////////////////////////////
function gameInit()
{
    // called once after the engine starts up
    // setup the game


    canvasFixedsize = vec2(1200, 720);
    for(let x=2;x<=levelSize.x-2; x+=2)
        for(let y=0;y<=levelSize.y; y++)
    { 
        const brick = new EngineObject(vec2(x,y), vec2(2,1));
        brick.color = randColor();
    
    }    

    cameraPos = levelSize.scale(.5);

}
///////////////////////////////////////////////////////////////////////////////
function gameUpdate()
{
    // called every frame at 60 frames per second
    // handle input and update the game state


    drawtect(cameraPos, vec2(100), new color(.5,.5,.5));
    drawtect(cameraPos, levelSize, new color(.1,.1,.1));

}
///////////////////////////////////////////////////////////////////////////////
function gameUpdatePost()
{
    // called after physics and objects are updated
    // setup camera and prepare for render
}

///////////////////////////////////////////////////////////////////////////////
function gameRender()
{
    // called before objects are rendered
    // draw any background effects that appear behind objects
}

///////////////////////////////////////////////////////////////////////////////
function gameRenderPost()
{
    // called after objects are rendered
    // draw effects or hud that appear above all objects
    (drawTextScreen, mainCanvasSize.scale(.5), 80);
}

///////////////////////////////////////////////////////////////////////////////
// Startup LittleJS Engine
engineInit(gameInit, gameUpdate, gameUpdatePost, gameRender, gameRenderPost, );
