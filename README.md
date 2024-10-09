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
        let languagesSpoken = languages.map { $0.spanishName }.joined(separator: ", ")
        let programmingLangs = programmingLanguages.joined(separator: ", ")
        let frameworksUsed = frameworks.joined(separator: ", ")
        let cloudTech = cloudStack.joined(separator: ", ")
        let dbTech = databasesStack.joined(separator: ", ")
        let markupLangs = markup.joined(separator: ", ")
        let skillsSet = skills.joined(separator: ", ")

        return """
        Hi, I'm \(name), a developer from \(location.description). I speak \(languagesSpoken).
        I work with programming languages like \(programmingLangs), and use frameworks such as \(frameworksUsed).
        I have experience with cloud technologies like \(cloudTech), databases like \(dbTech), and markup languages like \(markupLangs).
        My main skills are \(skillsSet).
        Feel free to reach me on LinkedIn: \(reachMe)
        """
    }
}

print(Daniel().composeGreeting())

```
