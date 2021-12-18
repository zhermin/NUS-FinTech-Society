# "NFT Appraisal with CNN"
_Personal Project for NUS FinTech Society_

### [Presentation Slides](./NUS%20FinTech%20Project%202%20Presentation%20-%20Tam%20Zher%20Min.pdf)
### [Kaggle Dataset by Arjan de Haan](https://www.kaggle.com/vepnar/nft-art-dataset)

---

## TLDR
* This was a project that "failed", ie. the results don't make sense (0% acc)
* Still had a lot of takeaways in project ideation and execution

## Motivation
* Had some experience with CNNs through own learning and current internship, so wanted to apply CNNs to Fintech
* Not a lot of CNN applications in Fintech space
    * Initially wanted to use CNN on vehicle insurance
    * Already an ongoing project at NUS Fintech so decided not to
* Thought about where else images are used in Fintech and thought of NFTs
* NFTs are usually images / pixel arts that carry a pricetag
* __So the idea was to train a CNN model that could learn what makes an image worth its value__
* And in turn, host a simple Streamlit website that uses the model to predict how much a random piece of artwork could be valued at

## Example: Cryptopunk #7523 sold for US11.75 million
![Cryptopunk #7523](./cryptopunk7523.png "Cryptopunk #7523")

## Execution Flow
1. Scrape or download large amounts of NFT images and their corresponding price data
2. Do some cleaning, eg. extracting the relevant information, scaling the prices
3. Split and feed the train/test data into a pretrained or custom CNN model with regressor
4. CNN model output has to be Dense(1) layer to get a continuous output
    * CNN + Regression is even more niche; but managed to find use case for predicting steering angles for self-driving cars using car camera feeds
5. ???
6. Profit

## Analysis
* Not understanding NFT pricing fundamentals
     * Was aware from the start that NFT prices usually don’t make sense
* But still wanted to test out my hypothesis that a model can learn
     * Hard to remove outliers and scale pricing data
* What constitutes as outliers?
     * Did not consider price changes over time
* Information that cannot be extracted from just an image

## Problems with NFT Prices
* NFTs are often fueled purely by speculation and social media hype
* This means they are often the vehicle for pump and dumps [[Castor, 2021]](https://tittlepress.com/crypto/834147/)
* "Half-Billion Dollar ‘Fake’ NFT Sale Becomes Real PR Stunt" [[Vold, 2021]](https://cryptonews.com/news/half-billion-dollar-fake-nft-sale-becomes-real-pr-stunt.htm)
     * Could have potentially sold to a gullible buyer at that price
     * Insane prices also from insider “bidding wars”
* They can also be part of money laundering schemes [[Woloszynski, 2021]](https://www.eisneramper.com/non-fungible-tokens-money-laundering-flvs-blog-0821/)
* These cause prices to make no sense and the underlying art be immaterial

## Improvements
* Change the problem statement and hypothesis
     * Instead of predicting prices from pixel positions on an image
* Alternative Idea: A More Traditional ML Method (No CNN)
    * Feed in social media sentiments and mentions
    * Feed in popularity of artist
    * Feed in NFT trait rarities to estimate scarcity
    * Simplify prediction output to range of prices instead of actual prices

## Conclusion
Although the idea was interesting, there were a lot of fundamental problems to how NFTs are priced that essentially made this impossible if purely relying on the NFT image themselves to predict its value. 

This is consistent with art in general, as even traditional arts such as physical paintings suffer from similar pricing problems that muddy the meaning to its prices. Issues such as money laundering were already prevalent with physical mediums, much less with digital ones that take a fraction of the time to generate the artpiece to simply be used as a vehicle to clean money. 

Some of the improvement pointers mentioned could help understand _why_ certain NFTs are priced in a certain way, although it would be impossible and even misguided to try and give a specific numerical value for an NFT. 

Nonetheless, this was an interesting problem statement and it definitely improved my understanding of NFTs and speculative assets as a whole. In essence, the pricing "fundamentals" of NFTs, or lack thereof, bear heavy semblance to the "meme" stocks of 2021, namely GameStop (GME) and AMC. Hence, future projects trying to tackle such unique "assets" could employ the same tactics that focus more on measuring the hype or popularity of the asset, rather than trying to price it using traditional methods such as fundamental analysis. 