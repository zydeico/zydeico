```swift
import Foundation

enum Location: String {
    case mexico = "Mexico"
}

enum Language: String {
    case spanish = "Spanish"
    case english = "English"
    
    var spanishName: String {
        switch self {
        case .spanish:
            return "Spanish"
        case .english:
            return "English"
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
    let skills = ["Mobile developer", "Backend developer", "AI & ML researcher"]
    private let reachMe = "LinkedIn: https://www.linkedin.com/in/jdanvz/"
    
    func composeGreeting() -> String {
        return """
        Hi, I'm \(name), a developer from \(location.rawValue). I speak \(languages.map { $0.spanishName }.joined(separator: ", ")).
        I work with programming languages like \(programmingLanguages.joined(separator: ", ")), and use frameworks such as \(frameworks.joined(separator: ", ")).
        I have experience with cloud technologies like \(cloudStack.joined(separator: ", ")), databases like \(databasesStack.joined(separator: ", ")), and markup languages like \(markup.joined(separator: ", ")).
        My main skills are \(skills.joined(separator: ", ")).
        Feel free to reach me on LinkedIn: \(reachMe)
        """
    }
}

print(Daniel().composeGreeting())

```
