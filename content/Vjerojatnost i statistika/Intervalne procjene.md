## Kvantil
* Realan broj $X_p$ za kojeg vrijedi $F(x_p) = p$ tj $\int_{-\infty}^{X_p} f(x)dx = p$ naziva se kvantil reda p.
## Interval povjerenja slučajne varijable
 * neka je p iz $<0,1>$, tada je interval $[c1, c2]$ za koji vrijedi $P(c_1 \leq X \leq c_2) = p$ naziva se interval povjerenja reda p za slučajnu varijablu X
 * za zadani $p \in <0,1>$, $\alpha = 1-p$  zovemo **nivo značajnosti**

pretpostavimo da postoje funkcije $\overline{\theta} (X_1, X_2, ..., X_n)$ i $\underline{\theta} (X_1, X_2, ..., X_n)$ takve da vrijedi $$P(\underline{\theta} \leq \vartheta \leq \overline{\theta}) = p$$Tada interval $<\underline{\theta}, \overline{\theta}>$ zovemo interval povjerenja reda rp za parametar $\vartheta$

## **Ključna ideja** za ono što slijedi 
Naći slučajnu varijablu koja ovisi o uzorku i o nepoznatom parametru kojeg procjenjujemo (ali ne o bilo kojem drugom nepoznatom parametru) za koju znamo njenu distribuciju (koja ne ovisi o nepoznatom parametru)

U nastavku pretpostavljamo da je $X \sim N(a, \sigma^2)$
1) Intervalna procjena očekivanja uz poznatu varijancu $\sigma^2$
Znamo da  $\overline{X} = \frac{1}{n} \sum_{i=1}^{n} X_i$  ima $E(\overline{X}) = a$ i $Var(\overline{X}) = \frac{\sigma^2}{n}$ pa je $\overline{X} \sim N(a, \frac{\sigma^2}{n})$
zbog stabilnosti normalne razdiobe $\overline{X} \sim N(a, \frac{\sigma^2}{n})$ slijedi da je $$\frac{\overline{X} - a}{\sqrt{\frac{\sigma^2}{n}}} \sim N(0,1)$$ ![[Pasted image 20250122184925.png]]
$$ P(-u_{1-\frac{\alpha}{2}} < \frac{\overline{X} - a}{\sqrt{\frac{\sigma^2}{n}}} < u_{1-\frac{\alpha}{2}}) = 1 - \alpha$$
$$ \rightarrow P(\overline{X} - u_{1-\frac{\alpha}{2}} \sqrt{\frac{\sigma^2}{n}} < a < \overline{X} + u_{1-\frac{\alpha}{2}} \sqrt{\frac{\sigma^2}{n}}) = 1 - \alpha$$

2) Interval procjene za očekivanje uz nepoznatu varijancu
Uz oznake $\overline{X}  = \frac{1}{n} \sum_{i=1}^{n} X_i$ i $S^2 = \frac{1}{n-1} \sum_{i=1}^{n} (X_i - \overline{X})^2$ poznato je $\frac{\overline{X} - a}{S/\sqrt{n}} \sim t(n-1)$
$$P(-t_{n-1,1-\frac{\alpha}{2}} < \frac{\overline{X} - a}{S/\sqrt{n}} < t_{n-1,1-\frac{\alpha}{2}}) = 1 - \alpha$$$$ \rightarrow P(\overline{X} - t_{n-1,1-\frac{\alpha}{2}} \frac{S}{\sqrt{n}} < a < \overline{X} + t_{n-1,1-\frac{\alpha}{2}} \frac{S}{\sqrt{n}}) = 1 - \alpha$$
3) Intervalna procjena varijance uz nepoznato očeivanje
Uz oznake $S^2 = \frac{1}{n-1} \sum_{i=1}^{n} (X_i - \overline{X})^2$ i vrijedi $\frac{(n-1)S^2}{\sigma^2} \sim \chi^2(n-1)$ pa slijedi
$$P(\chi^2_{n-1,\frac{\alpha}{2}} < \frac{(n-1)S^2}{\sigma^2} < \chi^2_{n-1,1-\frac{\alpha}{2}}) = 1 - \alpha$$
$$ \rightarrow P(\frac{(n-1)S^2}{\chi^2_{n-1,1-\frac{\alpha}{2}}} < \sigma^2 < \frac{(n-1)S^2}{\chi^2_{n-1,\frac{\alpha}{2}}}) = 1 - \alpha$$
dakle, $< \frac{(n-1)S^2}{\chi^2_{n-1,1-\frac{\alpha}{2}}}, \frac{(n-1)S^2}{\chi^2_{n-1,\frac{\alpha}{2}}} >$ je interval povjerenja za varijancu

4) Intervalna procjena za vjerojatnost događaja p
Neka je $X \sim \mathcal{B}(p)$
$X_1, X_2, ..., X_n$ jednoliko distribuirane $B(p) \rightarrow \sum_{i=1}^{n} X_i \sim B(n,p)$ 
$X_1 + X_2 + ... + X_n \approx \mathcal{N}(np, npq)$ 
$\overline{X} \approx \mathcal{N}(p, \frac{p(1-p)}{n})$ 
$\rightarrow \frac{\overline{X} - p}{\sqrt{\frac{p(1-p)}{n}}} \sim \mathcal{N}(0,1)$ 
označimo $\hat{p} = \overline{X}$ i dodatno pretpostavimo p u ... s $\hat{p}$ 
$$P(-u_{1-\frac{\alpha}{2}} < \frac{\hat{p} - p}{\sqrt{\frac{p(1-p)}{n}}} < u_{1-\frac{\alpha}{2}}) \approx 1 - \alpha$$
$$ \rightarrow P(\hat{p} - u_{1-\frac{\alpha}{2}} \sqrt{\frac{p(1-p)}{n}} < p < \hat{p} + u_{1-\frac{\alpha}{2}} \sqrt{\frac{p(1-p)}{n}}) \approx 1 - \alpha$$
