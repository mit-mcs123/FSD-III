Slip3:

Q.1 Develop a React app where a button toggles the visibility of a text.
Soln:
npx create-react-app toggles
cd toggles
npm start
App.js:
import React, { useState } from "react";
function App() {
  const [show, setShow] = useState(true);
  return (
    <div>
      <h2>Toggle Text Example</h2>
      <button onClick={() => setShow(!show)}>Show / Hide</button>
      {show && <p>This is some text!</p>}
    </div>
  );
}
export default App;


Q.2 Create a Simple Calculator app in Angular that performs addition, subtraction, multiplication, and division.
Soln:
ng new calculator-app
cd calculator-app
ng serve

app.html:
<h2>Simple Calculator</h2>
<input type="number" [(ngModel)]="num1" placeholder="Number 1">
<input type="number" [(ngModel)]="num2" placeholder="Number 2"><br><br>
<button (click)="add()">Add</button>
<button (click)="sub()">Sub</button>
<button (click)="mul()">Multi</button>
<button (click)="div()">Div</button>
<p>Result: {{ result }}</p>

app.ts:
import { Component } from '@angular/core';
import { CommonModule } from '@angular/common';
import { FormsModule } from '@angular/forms';
@Component({
 selector: 'app-root',
 standalone: true,
  imports: [CommonModule, FormsModule],
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  num1: number = 0;
  num2: number = 0;
  result: number | string = '';
add() {
    this.result = this.num1 + this.num2;
  }
sub() {
    this.result = this.num1 - this.num2;
  }
mul() {
    this.result = this.num1 * this.num2;
  }
div() {
    if (this.num2 !== 0) {
      this.result = this.num1 / this.num2;
    } else {
      this.result = 'Cannot divide by zero';
   }}}
