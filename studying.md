# CIA
**Confidentiality**, **Integrity** en **Availability**
## Confidentiality
Vertrouwelijkheid. 

Het **beperken van toegang** tot informatie.

Toegang wordt op basis van **gebruiksrecht** - **verschaft of ontzegd**.

## Integrity
Onveranderlijkheid of integriteit

Het garanderen dat informatie **niet ongewenst veranderd**

**Registreren** of **voorkomen** van wijzigingen.

## Availability
Beschikbaarheid

Informatie moet **wanneer benodigd** gebruikt kunnen worden door **gerechtigde partijen**. Raakvlakken met IT-beheer. 

Voorbeelden zijn: Fail-over (reduntant nodes in the data infrastructure), load-balancing, disaster recovery.

# Products
Combinaties van primitives en policies die direct toepasbaar zijn in de praktijk.

# VPN
Virtual Private Network

Drie soorten:
- Point-to-point
- Point-to-site
- Site-to-site

 Kan werken in de fysieke laag (laag 1), linklaag (laag 2) of in de internetlaag (laag 3) van het IP-model

 - OpenVPN: Gebruikt TLS, opereert in de internetlaag, werkt point-to-point, point-to-site en site-to-site
- IPSec: Opereert in de linklaag, site-to-site
- PPTP: Opereert in de linklaag, point-to-point
- VLAN: Opereert in de fysieke laag, site-to-sit

# Secure coding principles

## Minimaliseren van aanvalsvlakken
Hoe minder "poorten naar buiten", hoe veiliger. Meer ingangen betekend een grote kans op fouten dus ook meer vraag om beveiling.

- User interfaces
- Open ports
- Socket-verbindingen

## Verdediging in de diepte
Bouw je systeem als een soort ui met meerdere lagen van authorisatie en authenticatieslagen.

## Veilig falen

## Scheiding van verantwoordelijkheden (Authorisation management)

## Vermeid Security by Obscurity
Probeer niet een systeem veiliger te maken door het moeilijker te begrijpen te maken.

Ga er dus niet van uit dat de ontwikkelaar slimmer is dan alle andere mensen op aarde.

## Houdt security simpel
Hoe complexer het beveilingsontwerp, hoe groter de kans op fouten. En hoe groter de kans dat mensen het om zeep willen helpen.

## Continual improvement
PDCA cyclus

# TLS / HTTPS / SSL
Used for encryption and authentication

- Client vraagt om een SSL verbinding
- Server reageert met het SSL certificaat (die bevat ook de public key)
- Client valideert de public key / certificaat
- Client genereert een symmetrische sleutel (session key)
- Client versleuteld de symmetrische sleutel door middel van de public key
- Client stuurt de versleutelde symmetrische sleutel naar de server 
- De SSL verbinding is tot stand gekomen

## Certificate Signing Request
Een blok text die naar de CA gestuurd wordt bij het aanvragen van een SSL certificaat. Bevat informatie zoals de domein naam en organisatie maar ook de public key.

## Certificate Autority (CA)
Een vertroude derde partij die SSL certificaten afgeeft.

Door middel van centraal management kunnen certificaten ook weer ingetrokken worden.

## Root CA'S
Een partij zoals Verisign of Geotrust. Handelt geen klantaanvragen af

## Registration Authorities
Verstrekken SSL certificaten. Dit zijn vaak webhosts of overheden. Op basis van de ROOT CA geven zij weer certificaten af.

Sommigen RA's kunnen op basis van de ROOT CA zelf certificaten generegen. Hierdoor kunnen lange "certificate chains" ontstaan.



# DES: Data Encryption Standard
Oude standaard uit 1977 met een **56-bits** sleutel.

De sleutel is 64 bits waarbij elke byte (een byte is 8 bits) een **"parity bit"** bevat, hierdoor is de werkelijke waarde van de sleutel **56-bits**. (64 bits / 8 bits = 8 bits en 64 bits - 8 bits = 56 bits)  

**Chained Block Cipher** obv. **Feistel diagram**.

Later verbeterd door 3-dubble uitvoering (Triple DES of 3DES).

DES encryptie bestaat uit 16 ronden. Door middel van de originele 56-bits sleutel worden 16 deelsleutels gegenereerd (een deelsleutel per ronde).

## Permutatie
De karakters woorden omgezet naar een binair nummer. Vervolgens worden de waardes in het binaire nummer omgewisseld middels een **permutatietabel**. Deze tabel komt uit de DES standaard zelf.

Na de permutatie wordt de binaire sleutel in twee stukken verdeeld en worden er "left-shifts" uitgevoerd. Dit betekent dat de waardes van de twee helften "opgeschoven" worden. Na het opschuiven komen de twee helften weer samen om een deelsleutel te vormen.

Voor elke ronde wordt een nieuwe deelsleutel gegenereerd doormiddel van het bovenstaande proces.

# Diffie hellman

# Asymmetrische encryptie
Twee sleutels per partij, een sleutel voor encrypten en een sleutel voor decrypten.

**Toepassingen:**
- SSL/TLS
- Key exchange
- Smartcards
- SSH logins
- VPN

## Public key

## Private key


# AES: Advanced Encryption Standard
Huidige standaard voor symmetric block encryption met drie 

- Mogelijke sleutellengten: 128, 192 en 256 bits.
- Mogelijke ronden per operatie: 10, 12 of 14

Gegarandeerd 20 jaar secure.

# Realiseren van de CIA-driehoek
Dit doen we met **primitives**, **policies** en **products**.

## Primitives
Basisconcepten van cryptografie.

## Randomness / willekeur
Oorsprong en doel van cryptografie.

*Entropie*: Eenheid van willekeur

## Cryptographically Secure Pseudorandom Number Generators (CSPRNG's)
Computerfuncties die lange reeksen cijfers met een hoge mate van willekeur genereren.

Onderdeel van elk Operating System.

Interface met hardware vult entropy pool: CPU-klokken, stroomvoorziening, antennes etc.

Hash- of cryptofunctie (cipher), maakt uit pool langere random strings.

## Cryptofuncties
Encryptie + cryptografie

*Geheim schrijven*

**Plain text** wordt middels een **cryptofunctie** omgezet naar **ciphertext**

Is OMKEERBAAR (**encryption** en **decryption**)

## Typen encryptie
Worden bepaald door:
- Operatietypen in functie:
  - Substitutie
  - Transformatie
- Aantal sleutels:
  - Een - Symmetrisch
  - Twee - Asymmetrisch
- Operatiemodus:
  - Block
  - Stream

### Substitutie
Volgorde van karakters veranderd maar de karakters zelf veranderen niet.

### Transformatie
Karakters veranderen maar volgorde niet.

### Symmetrische encryptie
Een sleutel voor beide partijen. De sleutel veilig houden is lastig.

### Assymmetrische encryptie
Twee sleutels per partij, een sleutel voor encrypten en een sleutel voor decrypten.

Lastiger te implementeren maar veiliger in gebruik.

## Block ciphers
Versleuteling in "brokken" van gelijk formaat. Ieder blok dient als input voor het volgende blok. 

Voorbeelden zijn AES en DES

## Stream ciphers
Versleuteling in een continue stroom.

Sleutel maakt (psuedo)random data die wordt gecombineerd met de plaintext.

Voorbeelden zijn RC4 en ChaCha

## Policies
Beleid.

## Products
Implementatie van **Primitives** en **Policies**.

Combinatie van software, hardware en gedrag met het doel een organisatie te beveiligen.

Einddoel van informatiebeveiligingsproces.
