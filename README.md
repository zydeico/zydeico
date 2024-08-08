```swift

import Foundation

enum Location: String, CustomStringConvertible {
    case Mexico
    var description: String { rawValue }
}

enum Languages: String, CustomStringConvertible {
    case Spanish, English
    var description: String { rawValue }
    var spanishName: String {
        self == .Spanish ? "Español" : "Inglés"
    }
}

class Daniel {
    
    let name = "Daniel Vázquez"
    let location: Location = .Mexico
    let languages: [Languages] = [.Spanish, .English]
    let programmingLanguages = ["Swift", "Objective-C", "JavaScript", "Python"]
    let frameworks = ["NodeJS", "Django", "SwiftUI", "VueJS", "ReactJS"]
    let cloudStack = ["AWS", "Google Cloud Platform", "Azure"]
    let databasesStack = ["NoSQL", "SQL", "PostgreSQL", "MongoDB"]
    let markup = ["HTML", "CSS"]
    let introduction = "Hello world!, I'm software engineer, which are your superpower?"
    let skills = ["Mobile developer", "Backend developer", "IA & ML researcher"]
    private let reachMe = "Linkedin: https://www.linkedin.com/in/jdanvz/"
    
    func details() -> String {
        let mirror = Mirror(reflecting: self)
        let details = mirror.children.compactMap { child -> String? in
            guard let label = child.label, label != "reachMe" else { return nil }
            
            let value: String
            if label == "languages" {
                value = (child.value as? [Languages])?.map { $0.spanishName }.joined(separator: ", ") ?? ""
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
