```swift
import Foundation

enum Location: String, CustomStringConvertible {
    case mexico = "Mexico"
    
    var description: String {
        return rawValue
    }
}

enum Language: String, CustomStringConvertible {
    case spanish = "Spanish"
    case english = "English"
    
    var description: String {
        return rawValue
    }
    
    var spanishName: String {
        switch self {
        case .spanish:
            return "Español"
        case .english:
            return "Inglés"
        }
    }
}

class Daniel {
    
    let name = "Daniel Vázquez"
    let location: Location = .mexico
    let languages: [Language] = [.spanish, .english]
    let programmingLanguages = ["Swift", "Objective-C", "JavaScript", "Python", "TypeScript", "Kotlin", "Java"]
    let frameworks = ["NodeJS", "Django", "SwiftUI", "VueJS", "ReactJS", "NextJS", "JetPack Compose"]
    let cloudStack = ["AWS", "Google Cloud Platform", "Azure"]
    let databasesStack = ["NoSQL", "SQL", "PostgreSQL", "MongoDB"]
    let markup = ["HTML", "CSS"]
    let introduction = "Hello world! I'm a software engineer. What are your superpowers?"
    let skills = ["Mobile developer", "Backend developer", "AI & ML researcher"]
    private let reachMe = "LinkedIn: https://www.linkedin.com/in/jdanvz/"
    
    func details() -> String {
        let mirror = Mirror(reflecting: self)
        let details = mirror.children.compactMap { child -> String? in
            guard let label = child.label, label != "reachMe" else { return nil }
            
            let value: String
            if label == "languages" {
                value = (child.value as? [Language])?.map { $0.spanishName }.joined(separator: ", ") ?? ""
            } else if let array = child.value as? [CustomStringConvertible] {
                value = "[\(array.map { $0.description }.joined(separator: ", "))]"
            } else {
                value = String(describing: child.value)
            }
            
            return "\(label.capitalized): \(value)"
        }.joined(separator: "\n")
        
        return details + "\n\(reachMe)\n"
    }
}

print(Daniel().details())

```
