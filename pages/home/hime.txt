import { Component } from "@angular/core";
import { NavController } from "ionic-angular";

@Component({
  selector: "page-home",
  templateUrl: "home.html",
  styleUrls: ["home.css"]
})
export class HomePage {
  height: number;
  weight: number;
  intake: number;
  bmr: number;
  activeLevel: number;
  age: number;
  sex: string;

  constructor(public navCtrl: NavController) {}

  calculateIntake() {
    if (this.sex == "f") {
      this.bmr = 10 * this.weight + 6.25 * this.height - 5 * this.age - 161;
    } else if (this.sex == "m") {
      this.bmr = 10 * this.weight + 6.25 * this.height - 5 * this.age + 5;
    }
    this.intake = this.bmr * this.activeLevel;
    this.intake = parseFloat(this.intake.toFixed(2));
  }
}
