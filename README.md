```swift
import Foundation

enum Location: String {
    case Mexico
}

enum Languages: String {
    case Spanish
    case English
}

extension Location {
    var description: String {
        return self.rawValue
    }
}

extension Languages {
    var description: String {
        return self.rawValue
    }
}

class Developer {
    
}

class Daniel: Developer {

    let name = "Daniel Vázquez"
    let age = 30
    let location: Location = .Mexico
    let languages: [Languages] = [.Spanish, .English]

    let programmingLanguages = ["Swift", "Objective-C", "JavaScript", "Python"]
    let markup = ["HTML", "CSS", ""]

    func details() -> String {
        var details = ""
        for detail in Mirror(reflecting: self).children {
            guard let label = detail.label else { continue }
            
            // Check the type of detail.value and convert accordingly
            if let array = detail.value as? [CustomStringConvertible] {
                details.append("\(label.capitalized): [\(array.map { $0.description }.joined(separator: ", "))]\n")
            } else if let customDescription = detail.value as? CustomStringConvertible {
                details.append("\(label.capitalized): \(customDescription.description)\n")
            } else {
                details.append("\(label.capitalized): \(detail.value)\n")
            }
        }
        return details
    }
}

print(Daniel().details())
```

# Hello world!, I'm software engineer, which are your superpower?

## About Me 🙌🏻

* 📱  Apple platforms engineer

* 💻  Frontend Developer

* 👨🏻‍💻  Backend Developer

* 🔓  Former security analyst

* 🤖  AI researcher


## Reach me via 👇🏻

[Linkedin ](https://www.linkedin.com/in/jdanvz/)

