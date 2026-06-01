# LAB10DEV

dev-10
Rapport – LAB 10 : Navigation Drawer + Fragments Objectif Créer une app avec un menu latéral (NavigationDrawer) permettant de naviguer entre plusieurs Fragments dans une seule activité.

Concepts clés :

DrawerLayout + NavigationView

FragmentManager / FragmentTransaction

ListFragment

Étapes réalisées Étape Action 1 Créer projet avec template « Navigation Drawer Activity » 2 Modifier logo du menu et icônes dans res/menu/activity_main_drawer.xml 3 Créer fragments : AccueilFragment, ProfilFragment, ListeFragment 4 Modifier activity_main.xml : ajouter FrameLayout comme conteneur dynamique 5 Dans MainActivity.java : remplacer fragment au clic sur item du menu 6 Créer ListeFragment extends ListFragment avec un tableau de données 7 Exécuter et tester Extraits clés Transaction fragment :

java Fragment fragment = new AccueilFragment(); FragmentTransaction transaction = getSupportFragmentManager().beginTransaction(); transaction.replace(R.id.fragment_container, fragment); transaction.commit(); ListFragment simple :

java public class ListeFragment extends ListFragment { @Override public void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); String[] data = {"Item 1", "Item 2", "Item 3"}; setListAdapter(new ArrayAdapter<>(getActivity(), android.R.layout.simple_list_item_1, data)); } } Résultat attendu ✅ Menu latéral avec 3 options

✅ Clic → remplacement du fragment central

✅ Liste dynamique dans ListFragment
