# Named Entity Recognizer (NER) using Stanford CoreNLP

## Overview

This is a Java-based Named Entity Recognizer (NER) project built using **Stanford CoreNLP** and **Spring Boot**. It is designed as an exploratory step in my journey to understand **Natural Language Processing (NLP)** and lay a foundation for future projects in AI, including chatbots and language models.

Although the project is not currently functional due to Spring Boot launch issues (likely caused by Java version incompatibilities), I’m sharing it as part of my learning process and early experimentation with NLP technologies.

---

## Motivation

At the beginning of my sophomore year, I became deeply interested in building AI-powered chatbots. During my research, I realized that **understanding NLP is essential** to developing intelligent dialogue systems. While Stanford CoreNLP is not the latest toolkit available, it offers a clear and educational pipeline architecture which I found valuable for building foundational knowledge outside my formal coursework.

---

## Current Status

🔧 **Under Development**

- The Spring Boot application fails to launch successfully.
- The issue is suspected to be related to Java version mismatches.
- I may refactor or restart the project with a different approach but am publishing this as a record of my first attempt.

---

## Technologies Used

- **Java 17+** (ensure compatibility with your installed version)
- **Spring Boot** (Web, Thymeleaf, JSON, Logging)
- **Stanford CoreNLP** (v4.5.7) with models
- **JAXB** (for SUTime date recognition)
- **Apache Commons Lang**
- **Jackson for JSON Processing**
- **JollyDay** (for date parsing)

---

## Project Structure

```
src/
├── com.rizvi.nerapplication
│   ├── NerApplication.java              # Main Spring Boot Application
│   ├── controller/
│   │   └── NERController.java           # REST Controller for NER endpoint
│   ├── core/
│   │   └── Pipeline.java                # Stanford CoreNLP pipeline config
│   └── model/
│       └── Type.java                    # Enum for supported entity types
```

---

## How It Works (Planned)

1. A user sends a POST request to `/api/v1/ner` with:
   - The text to be analyzed.
   - A query parameter specifying the entity type (e.g., `Person`, `Location`, `Date`, etc.).

2. The server:
   - Initializes a Stanford CoreNLP pipeline.
   - Annotates the provided text.
   - Filters and extracts tokens matching the selected entity type.

3. A list of extracted named entities is returned as a JSON response.

---

## Example Usage (Planned)

```http
POST /api/v1/ner?type=Person
Content-Type: application/json

"Barack Obama was born in Hawaii."

Response:
[
  "Barack Obama"
]
```

---

## Enum Options

Supported entity types (defined in `Type.java`):

- `Person`
- `City`
- `State_Or_Province`
- `Country`
- `Email`
- `Date`
- `Time`
- `Money`
- `Percent`
- `Location`
- `URL`
- `Title`

---

## Build Dependencies (Excerpt from `pom.xml`)

```xml
<dependency>
  <groupId>edu.stanford.nlp</groupId>
  <artifactId>stanford-corenlp</artifactId>
  <version>4.5.7</version>
</dependency>
<dependency>
  <groupId>edu.stanford.nlp</groupId>
  <artifactId>stanford-corenlp</artifactId>
  <version>4.5.7</version>
  <classifier>models</classifier>
</dependency>
<!-- + Spring Boot, JAXB, and others -->
```

---

## Known Issues

- 🚫 Spring Boot does not start; likely due to Java version or dependency conflicts.
- 🔄 May restart the project with a simplified or alternative architecture.
- 📚 Still a learning-stage project — not ready for production use.

---

## Acknowledgments

- **Stanford CoreNLP** for its powerful yet educational tools in natural language processing.
- **Spring Boot** for simplifying web service deployment.
- My personal interest in AI, sparked by initial chatbot research, for motivating this journey into NLP.

---

## License

This project is shared under the MIT License as part of personal learning and exploration.

---

## Author

**Hasan Mustafa Rizvi**  
[LinkedIn](https://www.linkedin.com/in/hasan-mustafa-rizvi-595111288)  
Email: hxr9825@mavs.uta.edu

---

## Final Note

This project reflects my early attempt at understanding NLP by building a real-world application. It may not be complete or perfect, but it's a meaningful part of my growth as a developer and AI enthusiast.
