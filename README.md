// ==UserScript==
// @name         Mineparkour hack
// @namespace    http://tampermonkey.net/
// @version      1.0
// @description  Infinity jump and speedhack!
// @author       coolhacker
// @match        https://mineparkour.club/
// @icon         https://www.google.com/s2/favicons?domain=mineparkour.club
// @grant        none
// ==/UserScript==
 
(function() {
    'use strict';
    const oldSpeed = 80;
    const oldKeyDown = window.onkeydown;
    let infinityJump = false;
    let speedHack = false;
    window.onkeydown = (e)=>{
      if(e.code === 'Numpad7') infinityJump = !infinityJump;
      if(e.code === 'Numpad8') {
          speedHack = !speedHack;
          if(speedHack){
             window.speed = 300;
          } else{
             window.speed = oldSpeed;
          }
      }
        if(e.code === 'Space' && infinityJump){
           window.canJump = true;
        }
        if(oldKeyDown) oldKeyDown(e);
    }
})();
