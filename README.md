from textblob import TextBlob
import time

class SmartAnalyzer:
    def __init__(self):
        print("🤖 System: Smart Intelligence initialized.")

    def analyze_text(self, text):
        """Analyzes the sentiment of the input text using NLP."""
        blob = TextBlob(text)
        # Polarity ranges from -1 (Negative) to 1 (Positive)
        sentiment_score = blob.sentiment.polarity
        
        if sentiment_score > 0.1:
            return "🌟 Positive", sentiment_score
        elif sentiment_score < -0.1:
            return "💢 Negative", sentiment_score
        else:
            return "😐 Neutral", sentiment_score

if __name__ == "__main__":
    analyzer = SmartAnalyzer()
    
    print("\n--- Smart Sentiment AI ---")
    user_input = input("Enter a sentence to analyze (English): ")
    
    print("Analyzing...")
    time.sleep(1) # Simulating processing time
    
    label, score = analyzer.analyze_text(user_input)
    
    print("-" * 30)
    print(f"Input: {user_input}")
    print(f"Sentiment: {label}")
    print(f"Confidence Score: {round(score, 2)}")
    print("-" * 30)
