<template>
  <div>
    <h4>Cat Breeds</h4>

    <select v-model="selected">
      <option
        v-for="(breed, index) in breeds"
        v-bind:value="breed"
        :key="index"
        @select="filter = breed"
      >{{ breed.type }}</option>
    </select>
    <!-- <ul v-for="(breed, index) in breeds" :item="breed" :key="index"> -->
    <div>
      <p v-if="selected.id">{{ selected.type }}</p>
      <img v-if="selected.id" v-bind:src="selected.image" />
      <p v-if="selected.id">{{ selected.description }}</p>
    </div>
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
            'https://upload.wikimedia.org/wikipedia/commons/4/48/Abyssinian_Cat_Portrait.Idsfa.jpg',
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
        }
      ]
    }
  }
}
</script>

<style scoped>
h4 {
  color: red;
}
</style>
