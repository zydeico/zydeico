```swift

import Foundation

enum Location: String {
    case Mexico
}

enum Languages: String {
    case Spanish
    case English
    
    var spanishName: String {
        switch self {
        case .Spanish:
            return "Español"
        case .English:
            return "Inglés"
        }
    }
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
    let location: Location = .Mexico
    let languages: [Languages] = [.Spanish, .English]
    let programmingLanguages = ["Swift", "Objective-C", "JavaScript", "Python"]
    let frameworks = ["NodeJS", "SwiftUI", "VueJS", "ReactJS"]
    let cloduStack = ["AWS", "Google Cloud Platform", "Azure"]
    let markup = ["HTML", "CSS"]
    let introduction = "Hello world!, I'm software engineer, which are your superpower?"
    let skilss = ["Mobile developer", "Backend developer"]
    let reachMe = "Linkedin: https://www.linkedin.com/in/jdanvz/"

    func details() -> String {
        var details = ""
        
        for detail in Mirror(reflecting: self).children {
            
            guard let label = detail.label else { continue }
            
            if ["reachMe"].contains(label) {
                continue
            }
            
            if label == "languages" {
                if let languagesArray = detail.value as? [Languages] {
                    let languageNames = languagesArray.map { $0.spanishName }.joined(separator: ", ")
                    details.append("\(label.capitalized): \(languageNames)\n")
                }
            } else if let array = detail.value as? [CustomStringConvertible] {
                details.append("\(label.capitalized): [\(array.map { $0.description }.joined(separator: ", "))]\n")
            } else if let customDescription = detail.value as? CustomStringConvertible {
                details.append("\(label.capitalized): \(customDescription.description)\n")
            } else {
                details.append("\(label.capitalized): \(detail.value)\n")
            }
        }
        
        details.append("\(reachMe)\n")
        
        return details
    }
}

print(Daniel().details())

```
