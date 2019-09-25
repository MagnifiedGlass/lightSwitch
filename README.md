# lightSwitch

//
//  ViewController.swift
//  Light
//
//  Created by Adithya Pillai on 9/24/19.
//  Copyright © 2019 Adithya Pillai. All rights reserved.



import UIKit



class ViewController: UIViewController {
    
    var lightOn = true
    var blueShiftOn = false
    @IBOutlet weak var buttonChange: UIButton!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        updateUI()
        
    }
    
    @IBAction func buttonPressed(_ sender: Any) {
        lightOn = !lightOn
        updateUI()
    }
   
    @IBAction func BlueShiftPressed(_ sender: Any) {
        blueShiftOn = !blueShiftOn
        updateUI()
    }
    
    func updateUI (){
        if !lightOn {
            view.backgroundColor = .black
        } else if blueShiftOn {
            view.backgroundColor = .blue
        } else if  !blueShiftOn{
            view.backgroundColor = .white
        }
        
    }
    
}

