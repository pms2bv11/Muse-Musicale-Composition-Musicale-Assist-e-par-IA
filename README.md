# Muse-Musicale-Composition-Musicale-Assist-e-par-IA
Muse Musicale utilise des modèles de langage avancés et l'IA générative pour aider les compositeurs à créer des morceaux originaux et envoûtants, adaptés à différents styles musicaux.
import random

# Define basic musical elements
notes = ['A', 'B', 'C', 'D', 'E', 'F', 'G']
styles = {
    'classical': {'tempo': 'Adagio', 'key': 'C Major'},
    'jazz': {'tempo': 'Moderato', 'key': 'Bb Major'},
    'pop': {'tempo': 'Allegro', 'key': 'G Major'}
}
moods = ['happy', 'sad', 'energetic', 'relaxed']

# Function to generate a basic melody
def generate_melody(style, mood):
    melody = []
    for _ in range(8):  # Generate 8 notes for simplicity
        note = random.choice(notes)
        if mood == 'happy' or mood == 'energetic':
            # Higher chance for upbeat notes in happy or energetic moods
            if note in ['C', 'E', 'G']:
                note += "'"
        elif mood == 'sad' or mood == 'relaxed':
            # Lower chance for upbeat notes in sad or relaxed moods
            if note in ['A', 'B', 'D', 'F']:
                note += ","
        melody.append(note)
    return melody

# Main function to interact with the user
def main():
    print("Welcome to Muse Musicale: AI-Assisted Musical Composition")
    print("Please select a musical style from the following options:")
    for style in styles:
        print(style)
    selected_style = input("> ").lower()

    if selected_style not in styles:
        print("Invalid style selected.")
        return

    print("Please select a mood from the following options:")
    for mood in moods:
        print(mood)
    selected_mood = input("> ").lower()

    if selected_mood not in moods:
        print("Invalid mood selected.")
        return

    print(f"\nGenerating a {selected_mood} melody in the style of {selected_style}...")
    melody = generate_melody(selected_style, selected_mood)
    print("Generated Melody:", ' '.join(melody))
    print(f"Style Info: Tempo - {styles[selected_style]['tempo']}, Key - {styles[selected_style]['key']}")

if __name__ == "__main__":
    main()
