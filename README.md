import pandas as pd
books = pd.DataFrame({
'title': [
        'Amma diary lo koni pageulu',
        '826km',
        'The last melody',
        'Too good too be true',
        'The perfect us',
        'It ends with us',
        'Set on you',
        'Everyone has story',
        'I too had a love story',
        'War and Peace'
    ],
'genres': [
        'Fiction, Drama',
        'Dystopian, Fiction',
        'Fiction, Classic',
        'Fiction, Classic',
        'Fiction, Romance',
        'Fantasy, Adventure',
        'Dystopian, Fiction',
        'Dystopian, Fiction',
        'Fiction, Adventure',
        'Historical, Fiction'
    ]
})
def recommend_book(preferred_genre):
    recommended = books[books['genres'].str.contains(preferred_genre, case=False)]
    if recommended.empty:
        return "No recommendations found for this genre."
    
    return recommended['title'].tolist()
def main():
    print("Welcome to Book Recommendation System!")
    print("Available genres: Fiction, Drama, Dystopian, Classic, Romance, Fantasy, Adventure, Historical")
    preferred_genre = input("Please enter your preferred genre: ")
    recommendations = recommend_book(preferred_genre)
    if isinstance(recommendations, list):
        print("We recommend the following books:")
        for book in recommendations:
            print(f"- {book}")
    else:
        print(recommendations)

if __name__ == "__main__":
    main()






