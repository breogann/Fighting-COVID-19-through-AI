<p align="center">
  <img width="950" height="325" src="https://github.com/breogann/Fighting-COVID-19-through-AI/blob/master/Images/cover.png" alt="Fighting COVID-19">
</p>

# Prediction of coronavirus-binding pharmaceutical molecules using machine learning 💊 | 🦠

This Hackathon (_https://www.vencealvirus.com_) is an initiative from the Spanish government to create proposals in order to help with the coronavirus crisis 

👨🏻‍💻participants: [ireneisdoomed](https://github.com/ireneisdoomed),[mdemaic](https://github.com/MdeMaic),[breogann](https://github.com/breogann).

### Introduction 📖 ###

The main motivation behind this work is the use of AI algorithms to fight the lack of effective treatments for the disease created by SARS-CoV-2.

The whole scientific community is aiming to develop different strategies to stop the pandemic: vaccine development, synthetization of new molcules and also the use of the existint ones. The latter—adaptation of already comercialized molecules, is the way of action we worked on, since it's the best time-effective alternative.

A big problem in the pharma industry is to know whether a specific molecule can bind to a protein. Drug molecules are designed in such a way that its union to a specific viral protein change its structure, therefore leaving them inactive.

<p align="center">
  <img width="500" height="300" src="https://github.com/breogann/Fighting-COVID-19-through-AI/blob/master/Images/proteins.jpg" alt="proteins">
</p>

AI has a lot to offer in this field since the regular process of drug-screening is enduring and costful. Using an already trained neural network, we predicted the binding degree of more than 80 anti-viral drugs to the main proteins of the virus.

Under this paradigm, drug synthetization is based on four criteria: 

- Safe drugs in humans
- Active against COVID-19
- Feasibility of production
- Easily distributed

### Data 📊 ###

There are three main types of data we used:

- The virus proteins: proteins are chains of  aminoacids. These aminoacids can be represented using the __FASTA__ format: a string where every letter is a different aminoacid.

``````
>pdb|6YB7|A Chain A, SARS-CoV-2 main protease
SGFRKMAFPSGKVEGCMVQVTCGTTTLNGLWLDDVVYCPRHVICTSEDMLNPNYEDLLIRKSNHNFLVQA
GNVQLRVIGHSMQNCVLKLKVDTANPKTPKYKFVRIQPGQTFSVLACYNGSPSGVYQCAMRPNFTIKGSF
LNGSCGSVGFNIDYDCVSFCYMHHMELPTGVHAGTDLEGNFYGPFVDRQTAQAAGTDTTITVNVLAWLYA
AVINGDRWFLNRFTTTLNDFNLVAMKYNYEPLTQDHVDILGPLSAQTGIAVLDMCASLKELLQNGMNGRT
ILGSALLEDEFTPFDVVRQCSGVTFQ
``````

- The list of anti-viral drugs: Drugs can have different structures and compositions, so the notation is different. They are usually represented using the __SMILES__ notation:

``````
CC(C)CN(CC(C(CC1=CC=CC=C1)NC(=O)OC2COC3C2CCO3)O)S(=O)(=O)C4=CC=C(C=C4)N
``````

- The degree of binding affinity of the two previous data points: which depends on key pharmakinetic aspects of the molecules and is given by the neural network.

### Data processing 🛠 ###
 We created a dataset with all of these data so that we could work with it and get more information.

- For the FASTA's, we used web scrapping and regex to obtain the 55 sub-molecules that form all of the virus' proteins.
- For the list of drugs, we web-scrapped the drugbanked.ca site doing an anti-virals search.
- For the degree of binding affinity of these molecules, we used Selenium to automatize the execution of the more than 4.000 entries through the mt-dti.deargendev.me/dti site. 

<table border="0">
    <tr>
        <td><b style="font-size:13px">Used technologies 🔌</b></td>
        <td><b style="font-size:13px">Used libraries 📚</b></td>
    </tr>
    <tr>
        <td>
            <ul>
                <font size="1.5">
      <li>Selenium</li>
      <li>BeautifulSoup</li>
      <li>Regex</li>
      <li>Requests</li>
      </font>
            </ul>
        </td>
        <td>
            <ul>
                <font size="1.5">
      <li>PubChemPy</li>
      </font>
</table>

##### To do: #####
- Continue using Selenium to complete de dataset (possibly reducing the processing time)
- Reserch other potential drugs