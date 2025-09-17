
# TASK 0 =======
# Load in vectors for volume, price, and cryptocurrency asset names
load('Assignment1 - crypto_data.RData')
# vol_pct_chg: numeric vector. Percent change in average USD trading volume for each asset
#                 over the comparison window (e.g., last 7 days vs prior 7 days).
#                 Computed as 100 * (avg_current - avg_prior) / avg_prior.
#                 Positive = volume increased; negative = decreased.
#
# price_pct_chg: numeric vector. Percent change in average USD price for each asset
#                 over the same comparison window and formula as above.
#                 Positive = price increased; negative = decreased.
#
# asset: character vector. Human-readable cryptocurrency/crypto-asset names
#                 corresponding to each row (e.g., "Bitcoin", "Ethereum").
#
# Alignment note: asset[i], price_pct_chg[i], and vol_pct_chg[i] all refer to the same asset.
# For example, the first entry in asset corresponds to the first entries in price_pct_chg and vol_pct_chg.


# TASK 1 =======
# averages
average_price_pct_chg <- mean(price_pct_chg)
# ? Get average vol_pct_chg?
average_vol_pct_chg <- mean(vol_pct_chg)

# ? which asset has the highest volume percent change (vol_pct_chg)?

# TASK 2 =======
# Filter function
# ? Found this on Stack overflow... No idea how it works!
filter_func <- function(input_vector, records, filt_records){
  filt <- records %in% filt_records
  output_vector <- input_vector[filt]
  return(output_vector)
}

my_assets <- c("Bitcoin", "Ethereum", "Solana", "Cardano", "XRP", "Dogecoin")

# ? what are the sizes of the resulting vectors? Are they the same size?
filtered_price_pct_chg <- filter_func(input_vector = price_pct_chg,
                                      records = asset, 
                                      filt_records = my_assets)

filtered_vol_pct_chg <- filter_func(input_vector = vol_pct_chg,
                                    records = asset, 
                                    filt_records = my_assets)


# Task 3 ======
# Plots
plot(x = vol_pct_chg, 
     y = price_pct_chg,
     pch = 20,
     main = "Price % Change vs Volume % Change",
     xlab = "Volume % Change",
     ylab = "Price % Change"
)

for (i in 1:length(my_assets)){
  points(x = filtered_vol_pct_chg[i], y = filtered_price_pct_chg[i], pch = 8, col = "blue")
  text(x = filtered_vol_pct_chg[i], y = filtered_price_pct_chg[i], labels = my_assets[i], col = "gray",
       cex = .9, font = 1.5, pos = 4)
}
#  ? what does this mean?

