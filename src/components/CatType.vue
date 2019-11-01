<template>
  <div class="grid-container cat-type">
    <div class="grid-x grid-margin-x align-center">
      <div class="cell small-4">
        <select v-model="selected">
          <option
            v-for="(breed, index) in breeds"
            v-bind:value="breed"
            :key="index"
            @select="filter = breed"
            >{{ breed.type }}</option
          >
        </select>
      </div>
      <div v-if="selected.id" class="cell small-4">
        <div class="card">
          <img v-if="selected.id" v-bind:src="selected.image" />
          <div class="card-section">
            <p v-if="selected.id">{{ selected.type }}</p>
            <p v-if="selected.id">{{ selected.description }}</p>
          </div>
        </div>
      </div>
    </div>
    <!-- <ul v-for="(breed, index) in breeds" :item="breed" :key="index"> -->

    <!-- </ul> -->
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      selected: [],
      breeds: [
        {
          id: 1,
          type: 'Abyssinian',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/c/ca/Poktori-1.jpg',
          description:
            'The Abyssinian is a slender, fine-boned, medium-sized cat. The head is moderately wedge shaped, with a slight break at the muzzle, and nose and chin ideally forming a straight vertical line when viewed in profile. They have alert, relatively large pointed ears. The eyes are almond shaped and are gold, green, hazel or copper depending on coat color. The legs tend to be long in proportion to a graceful body, with small oval paws; the tail is likewise long and tapering.',
          selected: 'Abyssinian'
        },
        {
          id: 2,
          type: 'American Bobtail',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/3/3d/American_bobtail.jpg',
          description:
            'The American Bobtail is an uncommon breed of domestic cat which was developed in the late 1960s. It is most notable for its stubby "bobbed" tail about one-third to one-half the length of a normal cat\'s tail. This is the result of a cat body type genetic mutation affecting the tail development, similar to that of a Manx cat. The breed is not related to the Japanese Bobtail despite the similar name and physical type—the breeding programs are entirely unrelated, and the genetic mutation causing the bobbed tail are known to be different because the mutation causing the American Bobtail\'s tail is dominant, whereas the Japanese Bobtail tail mutation is recessive.',
          selected: 'American Bobtail'
        },
        {
          id: 3,
          type: 'American Curl',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/f/ff/American_curl.jpg',
          description:
            "The American Curl is a breed of cat characterized by its unusual ears, which curl back from the face toward the center of the back of the skull. An American Curl's ears should be handled carefully because rough handling may damage the cartilage in the ear. The breed originated in Lakewood, California, as the result of a spontaneous mutation.",
          selected: 'American Curl'
        },
        {
          id: 4,
          type: 'American Shorthair',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/d/d6/AmericanShorthairCat.JPG',
          description:
            'The American Shorthair is recognized in more than eighty different colors and patterns ranging from the brown-patched tabby to the blue-eyed white, the shaded silvers, smokes and cameos to the calico van, and many colors in between. Some even come in deep tones of black, brown, or other blends and combinations. Generally, only cats showing evidence of crossbreeding resulting in the colors chocolate, sable, lavender, lilac, or the point-restricted pattern of the Siamese family are disqualified from being shown.',
          selected: 'American Shorthair'
        },
        {
          id: 5,
          type: 'American Wirehair',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/7/7f/American_Wirehair_-_CFF_cat_show_Heinola_2008-05-04_IMG_8721.JPG',
          description:
            'American Wirehairs are similar to American Shorthairs, with the exception of a springy, wiry coat, including ear fur, and whiskers. This coat is similar to the wire coats of some dog breeds, such as terriers. Their fur requires little grooming, although lighter cats may require sunblock. Wirehairs are of a moderate, sturdy build, with round heads, high cheekbones, and a pronounced muzzle. Females are generally smaller than males. American Wirehairs display the full spectrum of possible cat coat colors, although Himalayan, Chocolate and Lilac are not accepted for competition. The Wirehair coat trait is dominant, so any breeding between a Wirehair and another cat can produce wired kittens. Wirehairs have golden eyes, except for some white ones that have blue or amber eyes.',
          selected: 'American Wirehair'
        },
        {
          id: 6,
          type: 'Asian Semi-longhair',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/a/a7/Tiffanie_at_cat_show.jpg',
          description:
            'The Asian Semi-Longhair is a cat breed similar to the Asian Shorthair except it has semi-long fur. The breed is also known by the name Tiffanie or Tiffany. It is recognized in any of the Asian Shorthair or Burmese colors and patterns. Like the Asian Shorthair, the breed was developed in Asia and is not currently recognized by any U.S. Registries. It has full recognition in the GCCF. It is related to, and in some registries distinct from, the Chantilly-Tiffany or Foreign Longhair, the North American variant.',
          selected: 'Asian Semi-longhair'
        },
        {
          id: 7,
          type: 'Australian Mist',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/4/42/Australian_Mist_%284985423018%29.jpg',
          description:
            'This breed was developed by Truda Straede in Australia beginning in 1975. The breed was developed by crossing the Burmese, Abyssinian, and miscellaneous domestic short-haired cats to create a short-haired cat with a spotted coat. The name was changed from "Spotted Mist" to "Australian Mist" in 1998, when cats with marbled coats, rather than spots, were accepted as part of the breed.',
          selected: 'Australian Mist'
        },
        {
          id: 8,
          type: 'Balinese',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/0/05/Old-Style_Balinese_Cat.png',
          description:
            'The Balinese is a long-haired breed of domestic cat with Siamese-style point coloration and sapphire-blue eyes. The Balinese is also known as the purebred long-haired Siamese, since it originated as a natural mutation of that breed and hence is essentially the same cat with a medium-length silky coat and a distinctively plumed tail.',
          selected: 'Balinese'
        },
        {
          id: 9,
          type: 'Bengal Cat',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/thumb/6/63/Panthera.jpg/1920px-Panthera.jpg',
          description:
            'The Bengal cat is a domesticated cat breed created from hybrids of domestic cats, the Asian leopard cat (Prionailurus bengalensis) and the Egyptian Mau, which gives them their golden shimmer – the breed name comes from the taxonomic name. Back-crossing to domestic cats is then done with the goal of creating a healthy, and docile cat with wild-looking, high-contrast coat.',
          selected: 'Bengal Cat'
        },
        {
          id: 10,
          type: 'Birman',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/a/ad/Birman-Cat.jpg',
          description:
            'Birmans have a medium-sized, rectangular body with a broad face and distinct Roman nose. Their ears are ideally as wide on the base as they are tall and should be set as much on top of the head as on the side. The eyes are rounded and should be a deep sapphire blue.',
          selected: 'Birman'
        },
        {
          id: 11,
          type: 'Bombay Cat',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/a/ac/Bombay_femelle.JPG',
          description:
            'The Bombay cat is a type of short-haired cat developed by breeding sable Burmese and black American Shorthair cats, to produce a cat of mostly Burmese type, but with a sleek, panther-like black coat. Bombay is the name given to black cats of the Asian group. Bombay cat is also called the Black Burmese, and nicknamed "mini-panther"',
          selected: 'Bombay Cat'
        },
        {
          id: 12,
          type: 'British Shorthair',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/9/9d/Britishblue.jpg',
          description:
            'The British Shorthair is the pedigreed version of the traditional British domestic cat, with a distinctively stocky body, dense coat, and broad face. The most familiar color variant is the "British Blue," a solid grey-blue coat, copper eyes, and a medium-sized tail. The breed has also been developed in a wide range of other colours and patterns, including tabby and colorpoint.',
          selected: 'British Shorthair'
        },
        {
          id: 13,
          type: 'Burmese',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/6/64/Burmakatze-rot.jpg',
          description:
            'The Burmese cat is a breed of domestic cat, originating in Thailand, believed to have its roots near the present Thai-Burma border and developed in the United States and Britain. Originally, all Burmese cats were dark brown (sable), but are now available in a wide variety of colours; formal recognition of these also varies by standard. Both versions of the breed are known for their uniquely social and playful temperament and persistent vocalisation.',
          selected: 'Burmese'
        },
        {
          id: 14,
          type: 'California Spangled Cat',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/6/6c/Star_Spangled_Cat.jpg',
          description:
            'The California Spangled is a breed of domestic cat that was bred to resemble spotted wild cats, like the ocelot and leopard. They were originally bred in the 1980s and were only ever a rare breed, with only 58 ever being registered. They were usually expensive, priced between US$800 and $2,500. The popularity of two other spotted cats breeds, the Ocicat and the Bengal, overshadowed their development.',
          selected: 'California Spangled Cat'
        },
        {
          id: 15,
          type: 'Chantilly-Tiffany Cat',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/5/5f/Tiffany3.jpg',
          description:
            'The Chantilly-Tiffany or Chantilly/Tiffany, also known as the Chantilly or the Foreign Longhair. The breed originated in North America. The Chantilly was thought extinct until the 1960s when two of these cats appeared during an estate sale. The Chantilly-Tiffany originated in a chocolate color, but later on was accepted in a range of colors including chocolate, blue, cinnamon, lilac, and fawn. Accepted patterns were solid, mackerel, ticked, and spotted tabby. The color was rich; shading in solids may occur toward the underside. The overall impression of an ideal Chantilly was a semi-foreign cat of striking appearance resulting from the combination of its rich color and full, silky semi-longhair coat, plumed tail, contrasting neck ruff, and ear furnishings.',
          selected: 'Chantilly-Tiffany Cat'
        },
        {
          id: 16,
          type: 'Chartreux',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/a/a4/0612_chartreux_vitscha_orsbleus.jpg',
          description:
            'The Chartreux is a rare breed of domestic cat from France and is recognised by a number of registries around the world. The Chartreux is large and muscular (called cobby) with relatively short, fine-boned limbs, and very fast reflexes. They are known for their blue (silver-grey) water-resistant short hair double coats which are often slightly nappy in texture (often showing "breaks" like a sheepskin) and orange- or copper-colored eyes. Chartreux cats are also known for their "smile": due to the structure of their heads and their tapered muzzles, they often appear to be smiling. Chartreux are exceptional hunters and are highly prized by farmers.',
          selected: 'Chartreux'
        },
        {
          id: 17,
          type: 'Chausie',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/0/03/Chausie_IMG_5149.jpg',
          description:
            'The Chausie is a domestic breed of cat that was developed by breeding a few individuals from the non-domestic species jungle cat (Felis chaus) to a far greater number of domestic cats (Felis silvestris catus). The Chausie was first recognized as a domestic breed by The International Cat Association (TICA) in 1995. Within the domestic breeds, the Chausie is categorized as a non-domestic hybrid source breed. ecause Chausies are mostly descended from domestic cats, by about the fourth generation they are fully fertile and completely domestic in temperament.',
          selected: 'Chausie'
        },
        {
          id: 18,
          type: 'Cheetoh',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/3/30/CheetohCatInGrass.jpg',
          description:
            'The Cheetoh’s parent breeds are the Ocicat and the Bengal, which is actually a direct descendant of the wild Asian Leopard Cat. These two breeds were crossed in 2001 by a breeder named Carol Drymon. She was hoping to create a new feline that would display the physical characteristics of a wild cat and the gentleness of a housecat. The plan was successful, and the Cheetoh is roughly eight generations removed from wild cats. Despite their good looks and great personality, however, Cheetohs are still rare compared to other breeds, particularly because this is a fairly new breed.',
          selected: 'Cheetoh'
        },
        {
          id: 19,
          type: 'Colorpoint Shorthair',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/4/4d/Colorpoint_Shorthair.jpg',
          description:
            'Colorpoint Shorthairs are a variety of domestic cat. Depending on the cat registry, they may be considered a separate breed of cat, or more often a variant of a pre-existing one, if accepted at all. These cats are distinguished by their conformance to wide range of sixteen different point colors, beyond the four standard Siamese colors. The variety was initially created by crossbreeding Siamese with the American Shorthair – the same mixture that created the Oriental Shorthair, but with different goals. The Colorpoint Shorthair shares the point-coloration pattern with the Siamese, but in the nontraditional colors of red, cream, tortoiseshell, and lynx (tabby) points, and minor variations thereof. In body style, head shape, and other features, it may be intermediate between the two foundation breeds, which show cats leaning toward Siamese traits. ',
          selected: 'Colorpoint Shorthair'
        },
        {
          id: 20,
          type: 'Cornish Rex',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/5/54/White_Cornish_Rex.jpg',
          description:
            'A Cornish Rex is a breed of domestic cat. The Cornish Rex has no hair except for down. Most breeds of cat have three different types of hair in their coats: the outer fur or "guard hairs", a middle layer called the "awn hair"; and the down hair or undercoat, which is very fine and about 1 cm long. Cornish Rexes only have the undercoat. They are prone to hair loss and many will develop a very thin coat or even go bald over large parts of their body. The curl in their fur is caused by a different mutation and gene than that of the Devon Rex. The breed originated in Cornwall, Great Britain. The coat of a Cornish Rex is extremely fine and sometimes curly. Their light coat means that they are best suited for indoor living in warm and dry conditions, as they are sensitive to low temperatures. They like to stay near warm places such as computer monitors, light bulbs, laps and shoulders.',
          selected: 'Cornish Rex'
        },
        {
          id: 21,
          type: 'Devon Rex',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/a/a0/Devon_rex_kitten_%28retouched%29.jpg',
          description:
            'The Devon Rex is a breed of intelligent, short-haired cat that emerged in England during the late 1950s. They are known for their slender bodies, wavy coat, and large ears. This breed of cat is capable of learning difficult tricks but can be difficult to motivate. The Devon Rex is a breed of cat with a curly, very soft short coat similar to that of the Cornish Rex. They are often associated with being one of the most hypoallergenic cats available because of their type of coat. However, they are technically not hypoallergenic.',
          selected: 'Devon Rex'
        },
        {
          id: 22,
          type: 'Don Sphynx',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/e/e8/Don_sphynx.jpg',
          description:
            "The Donskoy cat, also known as Don Sphynx or Russian Hairless, is a hairless cat breed of Russian origin. It is not related to the better-known mostly hairless breed of cat, the Sphynx cat, also known as the Canadian Hairless, whose characteristic hairlessness is caused by a recessive mutation in the keratin 71 gene, whereas the Donskoy's hairlessness is caused by a dominant mutation.",
          selected: 'Don Sphynx'
        },
        {
          id: 23,
          type: 'Egyptian Mau',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/7/7f/Egyptian_Mau_Bronze.jpg',
          description:
            'Egyptian Maus are a small- to medium-sized short-haired cat breed. They are one of the few naturally spotted breeds of domesticated cat. The spots of the Mau occur on only the tips of the hairs of its coat. It is considered to be a rare breed. The breed conformation is described as "a balance between the compactness of a Burmese and the slim elegance of a Siamese. Maus often possess very musical voices. They are known to chirp, chortle, and emit other distinctly unusual vocalizations when stimulated.',
          selected: 'Egyptian Mau'
        },
        {
          id: 23,
          type: 'Exotic Shorthair',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/c/c0/Yuri%2C_exotic_shorthair.jpg',
          description:
            "The Exotic Shorthair is a breed of cat developed as a short-haired version of the Persian. The Exotic is similar to the Persian in many ways, including temperament and conformation, a flat nose and face with the exceptions of the short dense coat. Exotic Shorthairs have a gentle and calm personality reminiscent of the Persian, but are generally livelier than their longhaired ancestors. Curious and playful, they are friendly to other cats and dogs, but they don't like being left alone and need the presence of their owner. ",
          selected: 'Exotic Shorthair'
        },
        {
          id: 24,
          type: 'Havana Brown',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/6/62/Brown_Burmese_Cat_Headshot.jpg',
          description:
            'The Havana Brown was the result of a planned breeding between Siamese and domestic black cats, by a group of cat fanciers in England, in the 1950s. Early breeders introduced a Siamese type Russian Blue into their breeding. However, using current genetic testing, it is believed that almost none remain in the gene pool.',
          selected: 'Havana Brown'
        },
        {
          id: 25,
          type: 'Himalayan',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/4/4e/Bartholomew_Kathmandu.jpg',
          description:
            "The Himalayan is a breed or sub-breed of long-haired cat similar in type to the Persian, with the exception of its blue eyes and its point colouration, which were derived from crossing the Persian with the Siamese. Some registries may classify the Himalayan as a long-haired sub-breed of Siamese, or a colorpoint sub-breed of Persian. The World Cat Federation has merged them with the Colorpoint Shorthair and Javanese into a single breed, the Colorpoint. Like many long-haired cats, Himalayans need to be brushed daily to keep their coats looking their best and healthiest. In addition, they may need their face wiped daily, depending on the cat. Bathing a Himalayan is also recommended by some breeders, to help reduce the amount of oil on the cat's fur and skin.",
          selected: 'Himalayan'
        },
        {
          id: 26,
          type: 'Japanese Bobtail',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/5/56/JapaneseBobtailBlueEyedMi-ke.JPG',
          description:
            'The Japanese Bobtail is a breed of domestic cat with an unusual bobtail more closely resembling the tail of a rabbit than that of other cats. The variety is native to Japan and Southeast Asia, though it is now found throughout the world. The breed has been known in Japan for centuries, and it frequently appears in traditional folklore and art. Recent scientific studies on cat genetics led by researchers has indicated that the Japanese Bobtail breed ranks amongst one of the most genetically diverse of pedigree breeds.',
          selected: 'Japanese Bobtail'
        },
        {
          id: 27,
          type: 'Javanese',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/6/6f/Javanese_cat.jpg',
          description:
            'The Javanese, also known as the Colorpoint (or Colourpoint) Longhair in some registries (though that name has other meanings), is a variety of purebred domestic cat. It is an Oriental-type, the long-haired equivalent of the Colorpoint Shorthair. The variety was developed in North America; its name is derived from the tradition of naming Oriental-type cats after Southeast Asian places. It is an offshoot of the Balinese breed, out-crossed to Siamese and Colorpoint Shorthair, and often having coat patterns not acceptable in those breeds. Individuals may or may not be have point coloration.',
          selected: 'Javanese'
        },
        {
          id: 28,
          type: 'Korat',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/c/c1/Veda%2Cchat-adulte-m%C3%A2le-race-korat.JPG',
          description:
            "The Korat  is a silver-tipped blue-grey, short-haired breed of domestic cat with a small to medium build and a low percentage of body fat. Its body is semi-cobby, and unusually heavy for its size. It is an intelligent and playful active cat that forms strong bonds with people. Among the Korat's distinguishing characteristics are its heart-shaped head and large green eyes.",
          selected: 'Korat'
        },
        {
          id: 29,
          type: 'LaPerm',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/5/5a/Laperm_LH_sealpoint.jpg',
          description:
            'he LaPerm is a breed of cat. A LaPerm\'s fur is curly (hence the name "perm"), with the tightest curls being on the belly, throat and base of the ears. LaPerms come in many colors and patterns. LaPerms generally have a very affectionate personality. They have an elegant and athletic build and are affectionate, active and outgoing in character. They are reputed to be hypoallergenic cats, provoking a significantly lower level of allergic response in humans than normal cats. Their most significant feature is their coat, which is made up of soft waves, curls and ringlets, resembling a shaggy perm.',
          selected: 'LaPerm'
        },
        {
          id: 30,
          type: 'Maine Coon',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/5/5a/Maine_Coon_cat_by_Tomitheos.JPG',
          description:
            'The Maine Coon is the largest domesticated cat breed. It has a distinctive physical appearance and valuable hunting skills. It is one of the oldest natural breeds in North America, specifically native to the state of Maine, where it is the official state cat. The Maine Coon is a large and sociable cat, hence its nickname, "the gentle giant." It is characterized by a prominent ruff along its chest, robust bone structure, rectangular body shape, an uneven two layered coat with longer guard hairs over a silky satin undercoat, and a long, bushy tail.',
          selected: 'Maine Coon'
        },
        {
          id: 31,
          type: 'Manx Cat',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/4/41/A_Rumpy_Manx_Cat.jpg',
          description:
            'The Manx cat is a breed of domestic cat originating on the Isle of Man, with a naturally occurring mutation that shortens the tail. Many Manx have a small stub of a tail, but Manx cats are best known as being entirely tailless; this is the most distinguishing characteristic of the breed, along with elongated hind legs and a rounded head. Manx cats come in all coat colours and patterns, though all-white specimens are rare, and the coat range of the original stock was more limited.',
          selected: 'Manx Cat'
        },
        {
          id: 32,
          type: 'Munchkin Cat',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/b/b8/Munchkin_Aliska_Karapuz.jpg',
          description:
            'The Munchkin cat or Sausage cat is a newer breed of cat characterized by its very short legs, which are caused by a genetic mutation. Much controversy erupted over the breed when it was recognized by The International Cat Association (TICA) in 1995 with critics voicing concern over potential health and mobility issues.',
          selected: 'Munchkin Cat'
        },
        {
          id: 33,
          type: 'Norwegian Forest Cat',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/9/98/NorwegianForestCat.jpg',
          description:
            "The Norwegian Forest cat is a breed of domestic cat originating in Northern Europe. This natural breed is adapted to a very cold climate, with a top coat of glossy, long, water-shedding hairs and a woolly undercoat for insulation. Although this is uncertain, the breed's ancestors may have been a landrace of short-haired cats brought to Norway by the Vikings around 1000 AD, who may also have brought with them long-haired cats, like those ancestral to the modern Siberian and Turkish Angora breeds. ",
          selected: 'Norwegian Forest Cat'
        },
        {
          id: 34,
          type: 'Ocicat',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/2/21/Ocicat-Charan.jpg',
          description:
            'The Ocicat is an all-domestic breed of cat which resembles a wild cat but has no recent wild DNA in its gene pool. The breed is unusual in that it is spotted like a wild cat but has the temperament of a domestic animal. It is named for its resemblance to the Ocelot. The breed was established from Siamese and Abyssinian stock; later, American Shorthairs (silver tabbies) were added to the mix and gave the breed their silver color, bone structure and distinct markings.',
          selected: 'Ocicat'
        },
        {
          id: 35,
          type: 'Ojos Azules',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/0/0f/Gato_Siam%C3%A9s_ojos_azules.JPG',
          description:
            'Ojos Azules is a breed of domestic cat. Unlike the blue eyes seen linked to the genes in bicolor cats and cats with point coloration, both of which suppress pigmentation, this gene is not linked to any certain fur color or pattern, giving the opportunity to have cats with dark coats and blue eyes. The depth of color in the eyes is greater even than that seen in a Siamese (cat), and does not cause squinting, deafness or cross-eye.',
          selected: 'Ojos Azules'
        },
        {
          id: 36,
          type: 'Oriental Longhair',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/6/65/OLH-GIP_Divan_Cesar.jpg',
          description:
            'Oriental Longhairs feature a long, tubular, Oriental-style body but with a longer silky coat. The range of possible coat colours includes everything from self-coloured (black, blue, chocolate, lilac, cinnamon, caramel, fawn, red, cream and apricot), tortoiseshell, smoke (silver undercoat), shaded or tipped, tabby or white. The eyes are almond shaped. The preferred eye color for Oriental Longhairs is green; except for the whites, which may have green or blue eyes, or be odd-eyed (two different colored eyes).',
          selected: 'Oriental Longhair'
        },
        {
          id: 37,
          type: 'Oriental Shorthair',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/6/6a/Oriental_shorthair_20070130_caroline.jpg',
          description:
            "The Oriental Shorthair is a breed of domestic cat developed from and closely related to the Siamese. It maintains the modern Siamese head and body type but appears in a wide range of coat colors and patterns. Like the Siamese, Orientals have almond-shaped eyes, a triangular head shape, large ears, and an elongated, slender, and muscular body. Their personalities are also very similar. Orientals are social, intelligent, and many are rather vocal. They often remain playful into adulthood, with many enjoying playing fetch. Despite their slender appearance, they are athletic and can leap into high places. They prefer to live in pairs or groups and also seek human interaction. Unlike the breed's blue-eyed forebear, Orientals are usually green-eyed.",
          selected: 'Oriental Shorthair'
        },
        {
          id: 38,
          type: 'Persian',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/1/15/White_Persian_Cat.jpg',
          description:
            'The Persian cat is a long-haired breed of cat characterized by its round face and short muzzle. It is also known as the "Persian Longhair" in the English-speaking countries. In the Middle East region, they are widely known as "Iranian cat" and in Iran they are known as "Shiraz cat". The first documented ancestors of the Persian were imported into Italy from Iran (historically known as Persia in the west) around 1620.',
          selected: 'Persian'
        },
        {
          id: 39,
          type: 'Pixie-Bob',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/a/a5/Uptoyou_duFarWestwithBePacific2.jpg',
          description:
            'The Pixie-bob is a breed of domestic cat claimed to be the progeny of naturally occurring bobcat hybrids. However, DNA testing has failed to detect bobcat marker genes, and Pixie-bobs are considered wholly domestic for the purposes of ownership, cat fancy registration, and import and export',
          selected: 'Pixie-Bob'
        },
        {
          id: 40,
          type: 'Ragamuffin',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/f/f3/20050922AmarilloRes.jpg',
          description:
            'Ragamuffins are a muscular, heavy breed of cat needing approximately four to five years to fully mature. The physical traits of the breed include a rectangular, broad-chested body with shoulders supporting a short neck. These cats are classified as having a "substantial" body type. Ragamuffins come in all coat colors and patterns, with a medium-length coat that increases in length toward the stomach. Although the coat is thick and plush, it does not readily mat or clump and is easy to care for.',
          selected: 'Ragamuffin'
        },
        {
          id: 41,
          type: 'Ragdoll',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/a/a3/Ragdoll_cat.jpg',
          description:
            'The Ragdoll is a cat breed with a color point coat and blue eyes. They are large and muscular semi-longhair cat with a soft and silky coat. Developed by American breeder Ann Baker in the 1960s, they are best known for their docile and placid temperament and affectionate nature. The name "Ragdoll" is derived from the tendency of individuals from the original breeding stock to go limp and relaxed when picked up.',
          selected: 'Ragdoll'
        },
        {
          id: 42,
          type: 'Russian Blue',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/3/3a/Russian_blue.jpg',
          description:
            "The Russian Blue is a cat breed that comes in colors varying from a light shimmering silver to a darker, slate grey. It is their short, dense coat which has been the hallmark of the Russian breed for more than a century. The dense coat stands out from the body. The Russian Blue is a naturally occurring breed that may have originated in the port of Arkhangel'sk in Russia. They are also sometimes called Archangel Blues. It is believed that sailors took Russian Blues from the Archangel Isles to Great Britain and Northern Europe in the 1860s.",
          selected: 'Russian Blue'
        },
        {
          id: 43,
          type: 'Russian White, Black, and Tabby',
          image:
            'http://www.russianblue.org.uk/BAC/blackwhite1_clip_image008.jpg',
          description:
            'The Russian White, Russian Black, and Russian Tabby are breeds of cat created in 1971, derived from the Russian Blue. The Black and Tabby Russians came from the original mating which created the Russian White. Today the Russian White is fully recognised in Australia, New Zealand, and South Africa and exists in various stages of recognition in the United Kingdom, many countries in mainland Europe, and the United States. In 2010 the American Cat Fanciers Association recognised the Russian Black and Russian White for championship status. ACFA Russian Shorthair Standard',
          selected: 'Russian White, Black, and Tabby'
        },
        {
          id: 44,
          type: 'Savannah',
          image:
            'https://en.m.wikipedia.org/wiki/Savannah_cat#/media/File%3ASavannah_Cat_portrait.jpg',
          description:
            'The Savannah is a hybrid cat breed. It is a cross between a serval and a domestic cat. The Savannah cat is the largest of the cat breeds. A Savannah cat is a cross between a domestic cat and a serval, a medium-sized, large-eared wild African cat. The unusual cross became popular among breeders at the end of the 1990s, and in 2001 The International Cat Association (TICA) accepted it as a new registered breed. In May 2012, TICA accepted it as a championship breed.',
          selected: 'Savannah'
        },
        {
          id: 45,
          type: 'Scottish Fold',
          image:
            'https://en.m.wikipedia.org/wiki/Scottish_Fold#/media/File%3AAdult_Scottish_Fold.jpg',
          description:
            'The Scottish Fold is a breed of domestic cat with a natural dominant-gene mutation that affects cartilage throughout the body, causing the ears to "fold", bending forward and down towards the front of the head, which gives the cat what is often described as an "owl-like" appearance.[',
          selected: 'Scottish Fold'
        },
        {
          id: 46,
          type: 'Selkirk Rex',
          image:
            'https://upload.wikimedia.org/wikipedia/en/c/c3/PolloSelkirkRex.jpg',
          description:
            'The Selkirk Rex is distinct from all other Rex breeds. Unlike the Devon Rex and Cornish Rex, the hair is of normal length and not partly missing. There are longhair and shorthair varieties. It differs from the LaPerm in that the Selkirk Rex coat is plusher and thicker. While the LaPerm gene is a simple dominant, the Selkirk gene (Se) acts as an incomplete dominant; incompletely dominant, allele pairs produce three possible genotypes and phenotypes: heterozygous cats (Sese) may have a fuller coat that is preferred in the show ring, while homozygous cats (SeSe) may have a tighter curl and less coat volume.',
          selected: 'Selkirk Rex'
        },
        {
          id: 47,
          type: 'Serengeti Cat',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/1/1a/Serengetimalecat.jpg',
          description:
            'The Serengeti is a breed of domestic cat, first developed by crossing a Bengal (domestic and wild hybrid) and an Oriental Shorthair. Recognized and registered by The International Cat Association (TICA), no other first generation crosses can be registered as Serengeti. From the Bengal × Oriental cross came the first foundation Serengeti. Breeders then worked with the cat to produce a cat that resembles the breed profile set by TICA. Created by Karen Sausman of Kingsmark Cattery in California in 1994, the breed is still in the development stages, but the ultimate aim is to produce a cat that looks similar to a serval, without using any recent wild cat blood.',
          selected: 'Serengeti Cat'
        },
        {
          id: 48,
          type: 'Siamese',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/2/25/Siam_lilacpoint.jpg',
          description:
            'The Siamese cat is one of the first distinctly recognized breeds of Asian cat. Derived from the Wichianmat landrace, one of several varieties of cat native to Thailand (formerly known as Siam), the Siamese became one of the most popular breeds in Europe and North America in the 19th century. The carefully refined modern Siamese is characterized by blue almond-shaped eyes; a triangular head shape; large ears; an elongated, slender, and muscular body; and various forms of point colouration.',
          selected: 'Siamese'
        },
        {
          id: 49,
          type: 'Siberian',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/0/0d/Siberian_Forest_Cat.jpg',
          description:
            'The Siberian is a landrace variety of domestic cat, present in Russia for centuries, and more recently developed as a formal breed, with standards promulgated since the late 1980s. They vary from medium to medium-large in size. A longer name of the formal breed is Siberian Forest Cat, but it is usually referred to as the Siberian or the Siberian cat. Another name for the formal breed is the Moscow Semi-Longhair.',
          selected: 'Siberian'
        },
        {
          id: 50,
          type: 'Singapura',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/5/5a/Moonwalker_the_Singapura.jpg',
          description:
            'The Singapura is one of the smallest breeds of cats, noted for its large eyes and ears, brown ticked coat, and blunt tail. Reportedly established from three "drain cats" imported from Singapore in the 1970s, it was later revealed that the cats were originally sent to Singapore from the US before they were exported back to the US. Investigations by the Cat Fanciers\' Association (CFA) concluded no wrongdoing and the Singapura kept its status as a natural breed.',
          selected: 'Singapura'
        },
        {
          id: 51,
          type: 'Snowshoe',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/d/d0/Fiona-gata-snowshoe.jpg',
          description:
            'The Snowshoe is a breed of cat originating in the United States of America in the 1960s. Snowshoes were first produced in Philadelphia when a Siamese breeder\'s cat gave birth to three kittens with white feet. The breeder, Dorothy Hinds-Daugherty, then began a breeding program to produce what were originally called "Silver Laces",[1] crossing the strangely marked Siamese cats with bi-color American Shorthair cats and other breeds.',
          selected: 'Snowshoe'
        },
        {
          id: 52,
          type: 'Somali',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/c/c6/Blue_Somali_kitten_age_3_months.jpg',
          description:
            'The Somali cat is often described as a long-haired African cat; a product of a recessive gene in Abyssinian cats, though how the gene was introduced into the Abyssinian gene pool is unknown. The Somalis are recognized for their bushy tails, large almond eyes, and large pointed ears, earning the breed its nickname of "Fox Cat." Their ticked coats, containing between four and twenty colors on each hair, are very fine in texture, making their coats softer to the touch than those of other cat breeds. The cat itself is medium-large in size.',
          selected: 'Somali'
        },
        {
          id: 53,
          type: 'Sphynx',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/e/e8/Sphinx2_July_2006.jpg',
          description:
            "The Sphynx cat is a breed of cat known for its lack of coat (fur). Hairlessness in cats is a naturally occurring genetic mutation; however, the Sphynx cat, as a breed, was developed through selective breeding, starting in the 1960s. The skin should have the texture of chamois, as it has fine hairs, or they may be completely hairless. Whiskers may be present, either whole or broken, or may be totally absent. They also have a narrow, long head, and webbed feet. Their skin is the color that their fur would be, and all the usual cat markings (solid, point, van, tabby, tortie, etc.) may be found on the Sphynx cat's skin. Because they have no coat, they lose more body heat than coated cats. This makes them warm to the touch and causes them to seek out sources of heat.",
          selected: 'Sphynx'
        },
        {
          id: 54,
          type: 'Tonkinese',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/b/b7/Tonkinese_Cat_-_Leo.jpg',
          description:
            'Tonkinese are a domestic cat breed produced by crossbreeding between the Siamese and Burmese. They share many of their parents\' distinctively lively, playful personality traits and are similarly distinguished by a pointed coat pattern in a variety of colors. In addition to the modified coat colors of the "mink" pattern, which is a dilution of the point color (as in watercolors), the breed is now being shown in the foundation-like Siamese and Burmese colors: pointed with white and solid overall (sepia). They are also now designated a natural breed, as their history has now determined them to have been extant since the 14th century.',
          selected: 'Tonkinese'
        },
        {
          id: 55,
          type: 'Toyger',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/c/ca/Toyger_-_Cornish_Rex_presentation_show_Riihim%C3%A4ki_2008-11-16_IMG_0101.JPG',
          description:
            'The toyger is a breed of domestic cat, the result of breeding domestic shorthaired tabbies (beginning in the 1980s) to make them resemble a "toy tiger", as its striped coat is reminiscent of the tiger\'s. The breed\'s creator, Judy Sugden, has stated that the breed was developed in order to inspire people to care about the conservation of tigers in the wild. It was recognized for "registration only" by The International Cat Association in the early 1990s, and advanced through all requirements to be accepted as a full championship breed in 2007. There are about 20 breeders in the United States and another 15 or so in the rest of the world, as of 2012.',
          selected: 'Toyger'
        },
        {
          id: 56,
          type: 'Turkish Angora',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/c/ca/Toyger_-_Cornish_Rex_presentation_show_Riihim%C3%A4ki_2008-11-16_IMG_0101.JPG',
          description:
            'The Turkish Angora  is a breed of a domestic cat. Turkish Angoras are one of the ancient, natural breeds of cat, having originated in central Turkey, in the Ankara region. The breed has been documented as early as the 17th century and is believed to be the origin of the mutations for both the coloration white and long hair. The breed is also sometimes referred to as simply the Angora or Ankara cat. Turkish Angora cats have long, silky coats and elegant, slender bodies, these bodies can sometimes grow to the length of limousines',
          selected: 'Turkish Angora'
        }
      ]
    }
  }
}
</script>

<style scoped>
.cat-type {
  padding-top: 60px;
}
</style>
