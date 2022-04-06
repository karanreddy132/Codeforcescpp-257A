# Codeforcescpp-257A
#include <bits/stdc++.h>
using namespace std;

int main() {
	int n, m, k, s[51];
	cin >> n >> m >> k;
	for (int i = 0; i < n; i++)
		cin >> s[i];

	sort(s, s + n, greater<int>());
	if (m <= k) {
		cout << 0;
		return 0;
	}
	int i = 0;
	while (m > 0 && i < n) {
		if (i == 0)
			m -= k - 1 + s[i];
		else
			m -= s[i] - 1;
		i++;
	}
	cout << (m > 0 ? -1 : i);
	return 0;
}
