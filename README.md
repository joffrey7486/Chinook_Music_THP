## a) Niveau facile

    Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?
`Album.all.length`
346

    Qui est l'auteur de la chanson "White Room" ?
`Track.find_by(title: "White Room").artist`
    
    Quelle chanson dure exactement 188133 milliseconds ?
`Track.find_by(duration: 188133).title`

    Quel groupe a sorti l'album "Use Your Illusion II" ?
`Album.find_by(title: "Use Your Illusion II").artist`

## b) Niveau Moyen

    Combien y a t'il d'albums dont le titre contient "Great" ? (indice)
`Album.where("title like ?", "%Great%").length`

    Supprime tous les albums dont le nom contient "music".
`Album.where("title like ?", "%music%").destroy`

    Combien y a t'il d'albums écrits par AC/DC ?
`̀Album.where("artist like ?", "AC/DC").count`

    Combien de chanson durent exactement 158589 millisecondes ?
`Track.where(duration: 158589).count`

## c) Niveau Difficile

Pour ces questions, tu vas devoir effectuer des boucles dans la console Rails. C'est peu commun mais c'est faisable, tout comme dans IRB.

    puts en console tous les titres de AC/DC.
`Track.where(artist: "AC/DC").each { |i| puts i.title }`

    puts en console tous les titres de l'album "Let There Be Rock".
̀̀`Track.where(album: "Let There Be Rock").each{|i| puts i.title}`

    Calcule le prix total de cet album ainsi que sa durée totale.
`Track.where(album: "Let There Be Rock").sum(:price)`
`Track.where(album: "Let There Be Rock").sum(:duration)`
    
    Calcule le coût de l'intégralité de la discographie de "Deep Purple".
`Track.where(artist: "Deep Purple").sum(:price)`

    Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.
`Track.where(artist: "Eric Clapton").each { |i| i.update(artist: "Britney Spears") }`

    
                                                         ProductBy Roobios, fleopaulD & joffrey7486