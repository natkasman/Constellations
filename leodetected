// Copyright (c) 2019 ml5
//
// This software is released under the MIT License.
// https://opensource.org/licenses/MIT

/* ===
ml5 Example
PoseNet example using p5.js
=== */

let video;
let poseNet;
let poses = [];

let noseX = 0;
let noseY = 0;
let leftWristX = 0;
let leftWristY = 0;
let rightWristX = 0;
let rightWristY = 0;

//Cancer
let imgCancer;
let CancerX1 = 600;
let CancerY1 = 300;
let CancerRad1 = 20;

let CancerX2 = 600;
let CancerY2 = 400;
let CancerRad2 = 20;

let CancerX3 = 500;
let CancerY3 = 500;


let CancerX4 = 700;
let CancerY4 = 500;

//Cassiopeia
let CassX1 = 100;
let CassY1 = 100;

let CassX2 = 200;
let CassY2 = 200;

let CassX3 = 300;
let CassY3 = 200;

let CassX4 = 500;
let CassY4 = 200;

let CassX5 = 400;
let CassY5 = 300;





function setup() {
  createCanvas(800, 600);
  video = createCapture(VIDEO);
  video.size(width, height);

  // Create a new poseNet method with a single detection
  poseNet = ml5.poseNet(video, modelReady);
  // This sets up an event that fills the global variable "poses"
  // with an array every time new poses are detected
  poseNet.on('pose', gotPoses)
  // poses = results;
  ;
  // Hide the video element, and just show the canvas
  video.hide();
}

function gotPoses(poses) {
  console.log(poses);
  if (poses.length > 0) {
    let newX = poses[0].pose.keypoints[10].position.x
    let newY = poses[0].pose.keypoints[10].position.y
    rightWristX = lerp(rightWristX, newX, 0.2);
    rightWristY = lerp(rightWristY, newY, 0.2);

    let newerX = poses[0].pose.keypoints[9].position.x
    let newerY = poses[0].pose.keypoints[9].position.y
    leftWristX = lerp(leftWristX, newerX, 0.2);
    leftWristY = lerp(leftWristY, newerY, 0.2);

  }
}

function modelReady() {
  select('#status').html('Model Loaded');
}

// function mousePressed(){
//   console.log(JSON.stringify(poses))
// }

// function drawGrid() {
//   // Cassiopeia
//   ellipse(100, 100, 20, 20)
//   ellipse(200, 200, 20, 20)
//   ellipse(300, 200, 20, 20)
//   ellipse(500, 200, 20, 20)
//   ellipse(400, 300, 20, 20)

  
  function drawCancer() {
  ellipse(CancerX1, CancerY1, 40);
  ellipse(CancerX2, CancerY2, 40);
  ellipse(CancerX3, CancerY3, 40);
  ellipse(CancerX4, CancerY4, 40);
} 

  function drawCass() {
  ellipse(CassX1, CassY1, 40);
  ellipse(CassX2, CassY2, 40);
  ellipse(CassX3, CassY3, 40);
  ellipse(CassX4, CassY2, 40);
  ellipse(CassX5, CassY5, 40);
} 

// function preload() {
//   imgCancer = loadImage('LeoConst');
// }


function draw() {
  background(20); 
  tint(255, 10);
  
  image(video, 0, 0, width, height);
    
  fill(255, 255, 255);
  ellipse(rightWristX, rightWristY, 10);
  ellipse(leftWristX, leftWristY, 10);
  
//   ellipse(CancerX1, CancerY1, 40);
//   ellipse(CancerX2, CancerY2, 40);
//   ellipse(CancerX3, CancerY3, 40);
//   ellipse(CancerX4, CancerY4, 40);
  
  
//       if (leftWristX > CancerX1 && leftWristX < CancerX1 + 40 && leftWristY > CancerY1 && leftWristY < CancerY1 + 40) {
        
//       fill(255, 0, 0);
//       text('word', width/2, height/2);
       
//    } else if (leftWristX > CancerX2 && leftWristX < CancerX2 + 40 && leftWristY > CancerY2 && leftWristY < CancerY2 + 40) {
//       fill(255, 0, 0);
//       text('word', width/2, height/2);
//    }
  

    if(dist(leftWristX, leftWristY, CancerX1, CancerY1) < CancerRad1) {
    //image(imgCancer,0,0);
    fill(0, 0, 255);
    }else{
    fill(255, 255, 255);
  }

  drawCancer();
  drawCass();
  // ellipse(CancerX1, CancerY1, CancerRad1*2, CancerRad1*2);
  // ellipse(CancerX2, CancerY2, CancerRad1*2, CancerRad1*2);
  // ellipse(CancerX3, CancerY3, CancerRad1*2, CancerRad1*2);
  // ellipse(CancerX4, CancerY4, CancerRad1*2, CancerRad1*2);


}
  
// CancerPoints();
    
// }

//   function CancerPoints() {
//   ellipse(CancerX1, CancerY1, CancerRad1*2, CancerRad1*2);
//   filter( BLUR, 6 );

//   }
