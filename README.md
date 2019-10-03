# lightSwitch

//
//  ViewController.swift
//  Light
//
//  Created by Adithya Pillai on 9/24/19.
//  Copyright © 2019 Adithya Pillai. All rights reserved.



import UIKit

class ViewController: UIViewController {
    var isPink = true
    var lightOn = true
    @IBOutlet weak var greySlider: UISlider!
    @IBOutlet weak var Label: UILabel!
    @IBOutlet weak var BlueValue: UILabel!
    @IBOutlet weak var BlueScale: UILabel!
    override func viewDidLoad() {
        super.viewDidLoad()
        updateUI()
    }
    
    @IBAction func SliderAction(_ sender: Any) {
        let color = greySlider.value
        view.backgroundColor = UIColor(red:(255 - CGFloat(color))/255, green: 255/255.0, blue: (255 + CGFloat(color))/255.0, alpha: 1.0)
        Label.text = String(greySlider.value)
    
    }
    @IBAction func buttonPressed(_ sender: UIButton) {
        lightOn = !lightOn
        if (lightOn) {
            Label.textColor = .black
            BlueValue.textColor = .black
            BlueScale.textColor = .black
            updateUI()
        } else if (!lightOn) {
            Label.textColor = .white
            BlueValue.textColor = .white
            BlueScale.textColor = .white
            updateUI()
        }
    }
    func updateUI() {
        if !isPink {
            view.backgroundColor = UIColor(red: 120/255.0, green: 126/255.0, blue: 217/255.0, alpha: 1.0)
        }
        else if lightOn {
            view.backgroundColor = .white
        } else {
            view.backgroundColor = .black
        }
    }
}


