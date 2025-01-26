
```cpp
#include <bits/stdc++.h>

using namespace std;

using ll = long long;

ll lcm(ll a, ll b) { return (a * b) / __gcd(a, b); }

int main()

{

    ios::sync_with_stdio(false);

    cin.tie(0);

    cout.tie(0);

    ll t;

    cin >> t;

    while (t--)

    {

        string n;

        cin >> n;

        vector<ll> v;

        for (int i = 0; i < n.size(); i++)

        {

            if (n[i] != '0')

            {

                v.push_back(n[i] - '0');

            }

        }

        ll l = 1;

        for (int i = 0; i < v.size(); i++)

        {

            l = lcm(l, v[i]);

        }

        ll s = stoll(n);

        ll r;

        ll ans = ((s + l-1) / l) * l;

        cout << ans << endl;

    }

}
```