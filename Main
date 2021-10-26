typedef long long ll;
const int M = 1e9 + 7;
const int N = 1005;
ll f[N], h[N];
ll power(ll x, int n) {
    if (n == 0)
        return 1;
    ll t = power(x, n / 2);
    if (n % 2)
        return t * t % M * x % M;
    return t * t % M;
}

long long legoWall(int n, int m) {

    for(register int i=0;i<n;i++) f[0] = 1;
    for(register int j=1;j<=m;j++) {
        f[j] = 0;
        for(register int k=1;k<=4;k++) {
            if (j >= k) {
                f[j] = (f[j] + f[j - k]) % M;
                h[j] = f[j];
            }
        }
    }
    for(register int j=1;j<=m;j++) {
        h[j] = power(h[j], n) % M;
        f[j] = h[j];
        for(register int k=1;k<=j-1;k++) {
            f[j] = (f[j] - h[k] * f[j - k] % M + M) % M;
        }
    }

    return f[m];
}
